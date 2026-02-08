

This report shows all personnel with their organizational structure and line manager information.

```dataviewjs
// 取得所有 People
const people = dv.pages('"Asset Management/Org/People"')
    .where(p => p["ci-type"] == "People")
    .sort(p => p.name, 'asc');

// 取得所有 Department 以便查詢 line manager
const departments = dv.pages('"Asset Management/Org/Department"')
    .where(d => d["ci-type"] == "Department");

// 取得所有 Division
const divisions = dv.pages('"Asset Management/Org/Division"')
    .where(d => d["ci-type"] == "Division");

dv.table(
    ["Name", "Title", "Division", "Department", "Line Manager"],
    people.map(person => {
        // 取得 Division 名稱
        let divisionName = "-";
        if (person.division) {
            const divLink = Array.isArray(person.division) ? person.division : person.division;
            if (divLink && divLink.path) {
                const divPage = dv.page(divLink.path);
                divisionName = divPage ? dv.fileLink(divLink.path, false, divPage.name) : "-";
            }
        }
        
        // 取得 Department 名稱和 Line Manager
        let departmentName = "-";
        let lineManager = "-";
        
        if (person.department) {
            const deptLink = Array.isArray(person.department) ? person.department : person.department;
            if (deptLink && deptLink.path) {
                const deptPage = dv.page(deptLink.path);
                if (deptPage) {
                    departmentName = dv.fileLink(deptLink.path, false, deptPage.name);
                    
                    // 從 Department 的 head 欄位取得 Line Manager
                    if (deptPage.head) {
                        const headLink = Array.isArray(deptPage.head) ? deptPage.head : deptPage.head;
                        if (headLink && headLink.path) {
                            const managerPage = dv.page(headLink.path);
                            lineManager = managerPage ? dv.fileLink(headLink.path, false, managerPage.name) : "-";
                        }
                    }
                }
            }
        }
        
        return [
            dv.fileLink(person.file.path, false, person.name),
            person.title || "-",
            divisionName,
            departmentName,
            lineManager
        ];
    })
);
```

---

## Statistics

```dataviewjs
const people = dv.pages('"Asset Management/Org/People"')
    .where(p => p["ci-type"] == "People");

const departments = dv.pages('"Asset Management/Org/Department"')
    .where(d => d["ci-type"] == "Department");

const divisions = dv.pages('"Asset Management/Org/Division"')
    .where(d => d["ci-type"] == "Division");

dv.paragraph(`
- **Total People**: ${people.length}
- **Total Departments**: ${departments.length}
- **Total Divisions**: ${divisions.length}
- **Last Updated**: ${new Date().toLocaleString('zh-TW')}
`);
```

---

## People by Department

```dataviewjs
const departments = dv.pages('"Asset Management/Org/Department"')
    .where(d => d["ci-type"] == "Department")
    .sort(d => d.name, 'asc');

const people = dv.pages('"Asset Management/Org/People"')
    .where(p => p["ci-type"] == "People");

dv.table(
    ["Department", "Head", "Member Count", "Members"],
    departments.map(dept => {
        // 取得 Department Head
        let headName = "-";
        if (dept.head) {
            const headLink = Array.isArray(dept.head) ? dept.head : dept.head;
            if (headLink && headLink.path) {
                const headPage = dv.page(headLink.path);
                headName = headPage ? dv.fileLink(headLink.path, false, headPage.name) : "-";
            }
        }
        
        // 從 member 欄位取得成員
        let memberNames = [];
        if (dept.member && Array.isArray(dept.member)) {
            memberNames = dept.member
                .filter(m => m && m.path)
                .map(m => {
                    const memberPage = dv.page(m.path);
                    return memberPage ? dv.fileLink(m.path, false, memberPage.name) : null;
                })
                .filter(m => m !== null);
        }
        
        // 也查詢反向關係（People 的 department 指向此 Department）
        const reversePeople = people
            .filter(p => {
                if (!p.department) return false;
                const deptLink = Array.isArray(p.department) ? p.department : p.department;
                return deptLink && deptLink.path === dept.file.path;
            })
            .map(p => dv.fileLink(p.file.path, false, p.name));
        
        // 合併兩種來源的成員
        const allMembers = [...new Set([...memberNames, ...reversePeople])];
        
        return [
            dv.fileLink(dept.file.path, false, dept.name),
            headName,
            allMembers.length,
            allMembers.length > 0 ? allMembers.join(", ") : "None"
        ];
    })
);
```
