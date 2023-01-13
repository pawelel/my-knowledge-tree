---
{"title":"Visual Studio Code","dg-publish":true,"tags":["software"],"language":"en","permalink":"/software/visual-studio-code/","dgPassFrontmatter":true}
---

up:: [[software/Software\|Software]]

Visual Studio Code can be used as default text editor and IDE for apps written in JavaScript, [[coding/TypeScript/TypeScript\|TypeScript]], [[coding/CSharp/CSharp\|CSharp]] and other languages.

## C4-PlantUML - a VS Code extension for C4 Model

PlantUML is a plugin for VS Code, that supports rendering of C4 Model.  
- [Intro to C4 Architecture Diagrams and C4 PlantUML extension](https://www.youtube.com/watch?v=n-e1FDAtBuM)  
- [Plugin repository](https://github.com/plantuml-stdlib/C4-PlantUML)

## DocFx Toc Generator

Generates a Table of Contents (TOC) in YAML format for DocFX. A useful extension for those who create documentation with DocFX

## Switch to terminal/editor
To switch between terminal and editor you can use `Ctrl` + `J` or `TAB` + \`.

## Find file
Press `Ctrl`+ `P` and start typing file name.

## YAML frontmatter snippet - add file and folder name
The code below allows you to insert folder name as a tag and file name as title using command: `Ctrl`+`Space` and `T`
```json
"yaml title": {
		"prefix": "t",
		"body": ["---",
			"title: $0${TM_FILENAME_BASE}",
			"tags: ${TM_DIRECTORY/^.+\\\\(.*)$/$1/}",
			"---"
		],
		"description": "yaml title"
	}
```