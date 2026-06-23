<%*
let title = tp.file.title;
await tp.file.rename(title + tp.date.now("YYYYMMDDHHmmss"));

tR += "---\n";
tR += "Title: " + title + "\n";
tR += "Priority: undef\n";
tR += "Await: \n"
tR += "Due: " + tp.date.now("YYYY-MM-DDTHH:mm") + ":00\n";
tR += "tags:\n";
tR += "  - " + title + "\n";
tR += "---\n";
%>