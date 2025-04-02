# PHYS-2305


## Lectures
```dataviewjs
const {createButton} = app.plugins.plugins["buttons"]
app.plugins.plugins["Templater"]

let h = dv.current().file.folder.toString();
h = h+"/Lectures"

var j = 	dv.pages()
	.where(k => k.file.folder == h)
	.sort(k => k.lecture, 'asc').lecture.last();

if (j) {
	j=j+1;
} else {
	j=1
}
const r = ('0' + j.toString()).slice(-2);
const fname = h+"/"+dv.current().file.name+".L"+r

dv.paragraph(createButton({
	app, 
	el: this.container, 
	args: {
		name: "Next lecture: "+j, 
		type: "note("+fname+", split) template", 
			action: "Lecture Note", 
		color: "yellow",
	}
}))
```

```dataview
table WITHOUT ID "[["+file.name+"|Lecture "+lecture+"]]" as lecture, date,   topics, rec, coursenotes
sort lecture
where course = this.file.link and (lecture or lecture = 0)
```
