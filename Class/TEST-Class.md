---
tags:
  - Class
---

> [!cards]
> ```meta-bind-button
> style: primary
> label: Add Page
> id: add-project-default
> action:
>   type: templaterCreateNote
>   templateFile: "Template/Page.md"
>   folderPath: "Pages"
>   fileName: TEST-Class
> ```
> ```meta-bind-button
> style: primary
> label: Add Flash
> id: add-project-default
> action:
>   type: templaterCreateNote
>   templateFile: "Template/Flash.md"
>   folderPath: "Pages"
>   fileName: TEST-Class
> ```
# Notes
```dataviewjs
dv.table(
  ["Note", "Created"],
  dv.pages('#TEST-Class')
    .sort(p => p.file.frontmatter.title, 'asc')    .map(p => [
        dv.fileLink(p.file.path, false, p.file.frontmatter.Title),
        p.file.frontmatter.Created
    ])
)
```

# Flash
```dataviewjs
dv.table(
  ["Flash", "Created", "Count"],
  dv.pages('#TEST-Class and #flash')
    .sort(p => p.file.frontmatter.created, 'asc')    .map(p => [
        dv.fileLink(p.file.path, false, p.file.frontmatter.Title),
        p.file.frontmatter.Created,
        p.file.frontmatter.Count
    ])
)
```
 
