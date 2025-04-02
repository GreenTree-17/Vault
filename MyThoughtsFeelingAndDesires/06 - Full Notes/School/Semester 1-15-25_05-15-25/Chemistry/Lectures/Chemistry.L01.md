---
created: <% tp.file.creation_date("YYYY-MM-DDTHH:mm:ss") %>
modified: <% tp.file.last_modified_date("YYYY-MM-DDTHH:mm:ss") %>
tags: [lecture]
topics:
 - <% tp.file.cursor(2) %>
---
<%*
  let title = tp.file.title;
  var course = title.slice(0,-4);
  var lecture = title.slice(-2);
  lecture = Number(lecture);
%>
# <%* tR += `${course}` %> Lecture <%* tR += `${lecture}` %>
- [i] course:: [[<%* tR += `${course}` %>]]
- [i] date:: <% tp.file.creation_date("YYYY-MM-DDTHH:mm:ss") %>
- [i] lecture:: <%* tR += `${lecture}` %>
- [i] rec:: 

# <% tp.file.cursor(1) %>


---
- [i] CourseNotes:: 