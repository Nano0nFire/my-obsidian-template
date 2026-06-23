<%*
let title = tp.file.title;
await tp.file.rename(title + tp.date.now("YYYYMMDDHHMMSS"));

tR += "---\n";
tR += "Title: Flash-" + title + "\n";
tR += "Created: " + tp.date.now("YYYY-MM-DDTHH:MM") + ":00\n";
tR += "Count: 0\n";
tR += "Due: " + tp.date.now("YYYY-MM-DDTHH:MM") + ":00\n";
tR += "tags:\n";
tR += "  - " + title + "\n";
tR += "  - flash/" + title + "\n";
tR += "---\n";
%> 