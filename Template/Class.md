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
<%*
let title = tp.file.title
if (title.startsWith("Untitled")) {
	title = await tp.system.prompt("Class Name");
	await tp.file.rename(title)
}

tR += ">   fileName: " + title + "\n";
tR += "> ```\n"
tR += "> ```meta-bind-button\n"
tR += "> style: primary\n"
tR += "> label: Add Flash\n"
tR += "> id: add-project-default\n"
tR += "> action:\n"
tR += ">   type: templaterCreateNote\n"
tR += ">   templateFile: \"Template/Flash.md\"\n"
tR += ">   folderPath: \"Pages\"\n"
tR += ">   fileName: " + title + "\n";
tR += "> ```\n"
tR += "# Notes\n"
tR += "```dataviewjs\n"
tR += "dv.table(\n"
tR += "  [\"Note\", \"Created\"],\n"
tR += "  dv.pages('#" + title + "')\n"
tR += "    .sort(p => p.file.frontmatter.title, 'asc')"
tR += "    .map(p => [\n"
tR += "        dv.fileLink(p.file.path, false, p.file.frontmatter.Title),\n"
tR += "        p.file.frontmatter.Created\n"
tR += "    ])\n"
tR += ")\n"
tR += "```\n\n"
tR += "# Flash\n"
tR += "```dataviewjs\n"
tR += "dv.table(\n"
tR += "  [\"Flash\", \"Created\", \"Count\"],\n"
tR += "  dv.pages('#" + title + " and #flash')\n"
tR += "    .sort(p => p.file.frontmatter.created, 'asc')"
tR += "    .map(p => [\n"
tR += "        dv.fileLink(p.file.path, false, p.file.frontmatter.Title),\n"
tR += "        p.file.frontmatter.Created,\n"
tR += "        p.file.frontmatter.Count\n"
tR += "    ])\n"
tR += ")\n"
tR += "```\n"
%> 
