---
created: <% tp.file.creation_date("YYYY-MM-DDTHH:mm:ss") %>
modified: <% tp.file.last_modified_date("YYYY-MM-DDTHH:mm:ss") %>
tags:
  - lecture
topics:
  - <% tp.file.cursor(2) %>
Course: [[<%* tR += `${course}` %>]]
lecture: <%* tR += `${lecture}` %>
date: <% tp.file.creation_date("YYYY-MM-DDTHH:mm:ss") %>
rec:
---
<%*
  let title = tp.file.title;
  var course = title.slice(0,-4);
  var lecture = title.slice(-2);
  lecture = Number(lecture);
%>
# <%* tR += `${course}` %> Lecture <%* tR += `${lecture}` %>

# <% tp.file.cursor(1) %>


---
- [i] CourseNotes:: 