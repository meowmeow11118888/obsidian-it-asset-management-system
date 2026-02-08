
```dataviewjs
// 查詢所有 Server 並找出其關聯的 Application 和 Service
const servers = dv.pages('"Asset Management/CI/Server"')
    .where(p => p["ci-type"] == "Server");

// 取得所有 Application 和 Service 以便反向查詢
const applications = dv.pages('"Asset Management/CI/Application"');
const services = dv.pages('"Asset Management/CI/Service"');

// 建立表格
dv.table(
    ["Server Name", "IP", "Applications", "Services", "Status", "Primary Admin"],
    servers.map(server => {
        // 找出部署在此 Server 上的 Applications
        const appsOnServer = applications
            .where(app => {
                const hostedOn = app["hosted-on-server"];
                if (!hostedOn) return false;
                // 處理單一連結或陣列連結
                const links = Array.isArray(hostedOn) ? hostedOn : [hostedOn];
                return links.some(link => 
                    link && link.path === server.file.path
                );
            });
        
        // 找出使用這些 Applications 的 Services
        const servicesForServer = services
            .where(service => {
                const runsOn = service["runs-on-application"];
                if (!runsOn) return false;
                const serviceLinks = Array.isArray(runsOn) ? runsOn : [runsOn];
                return appsOnServer.some(app => 
                    serviceLinks.some(link => 
                        link && link.path === app.file.path
                    )
                );
            });
        
        // 格式化顯示
        const appNames = appsOnServer.length > 0 
            ? appsOnServer.map(a => a.name).join(", ") 
            : "None";
        
        const serviceNames = servicesForServer.length > 0
            ? servicesForServer.map(s => s.name).join(", ")
            : "None";
        
        return [
            server.name,
            server["ip-address"] || "N/A",
            appNames,
            serviceNames,
            server["server-status"] || "Unknown",
            server["primary-admin"] || "N/A"
        ];
    })
);
```

