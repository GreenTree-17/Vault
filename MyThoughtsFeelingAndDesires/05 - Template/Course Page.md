# PHYS-2305


## Lectures
```dataviewjs
	const mb = app.plugins.getPlugin('obsidian-meta-bind-plugin')?.api;
	
	let fPath = dv.current().file.folder.toString();
	fPath = fPath+"/Lectures";
	
	var j = 	dv.pages()
		.where(k => k.file.folder == fPath)
		.sort(k => k.lecture, 'asc').lecture.last();
	
	if (j) {
		j=j+1;
	} else {
		j=1;
	}
	const r = ('0' + j.toString()).slice(-2);
	const fname = fPath+"/"+dv.current().file.name+".L"+r;
	const buttonConfig = {
		label: "Next lecture: "+j,
		style: 'primary',
		action: {
			type: "templaterCreateNote",
			templateFile: "05 - Template/Lecture Note",
			folderPath: fPath,
			fileName: fname,
			openNote: true,
			hidden: false,
			id: "Lecture",
		}
	};
	const buttonOptions = {
		declaration: buttonConfig,
		isPreview: false
	};
	const container = document.createElement("div");
	
	const button = mb.createButtonMountable(dv.current().file.toString(), buttonOptions);
	const activeView = app.workspace.activeLeaf.view;
	
	mb.wrapInMDRC(button, container,activeView);
	document.querySelector('.view-content').appendChild(container);
```




```dataview
table WITHOUT ID "[["+file.name+"|Lecture "+lecture+"]]" as lecture, date,   topics, rec, coursenotes
sort lecture
where course = this.file.link and (lecture or lecture = 0)
```
