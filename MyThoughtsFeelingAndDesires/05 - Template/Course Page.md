# PHYS-2305


## Lectures
```dataviewjs
	const mb = app.plugins.getPlugin('obsidian-meta-bind-plugin')?.api;
	
	let h = dv.current().file.folder.toString();
	h = h+"/Lectures";
	
	var j = 	dv.pages()
		.where(k => k.file.folder == h)
		.sort(k => k.lecture, 'asc').lecture.last();
	
	if (j) {
		j=j+1;
	} else {
		j=1;
	}
	const r = ('0' + j.toString()).slice(-2);
	const fname = h+"/"+dv.current().file.name+".L"+r;
	const buttonConfig = {
		label: "Next lecture: "+j,
		style: 'primary',
		action: {
			type: "templaterCreateNote",
			templateFile: "05 - Template/Lecture Note",
			folderPath: h,
			fileName: fname,
			openNote: "true"
		},
	};
	const buttonOptions = {
		declaration: buttonConfig,
		isPreview: false,
	};
	const container = document
	
	const button = mb.createButtonMountable(context.file.path, buttonOptions);
	mb.wrapInMDRC(button, container, component)
```


```dataview
table WITHOUT ID "[["+file.name+"|Lecture "+lecture+"]]" as lecture, date,   topics, rec, coursenotes
sort lecture
where course = this.file.link and (lecture or lecture = 0)
```
