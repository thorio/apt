---
layout: null
---

<style>
html {
	font-family: Arial, Helvetica, sans-serif;
	background-color: #181a1b;
	color: #e8e6e3;
}

body {
	max-width: 100ch;
	margin: auto;
	padding: 0 1rem;
}

h1 {
	margin: 4rem 0;
	text-align: center;
}

hr {
	margin: 2rem;
	border: 1px solid #666;
}

div.highlight {
	background-color: #121414;
	padding: 1rem;
}

pre.highlight {
	margin: 0;
}

code {
	overflow-x: auto;
	white-space: pre-line;
}

thead th:first-child {
	width: 200px;
}

td {
	background-color: #121414;
	padding: 3px 7px;
}
</style>

# thorio's personal apt repo

This contains some of my software. These packages *should* work on debian and derivatives, though I don't know which versions specifically.

This is intended for my own machines, so **I don't recommend others use this repo.** Potential nasal demons ahead.

* * *

## Installation

Install requisite packages:

```bash
apt-get update
apt-get install apt-transport-https ca-certificates curl gnupg
```

Add the gpg key:

```bash
curl -fsSL https://thorio.github.io/apt/gpg | sudo gpg --dearmor -o /usr/share/keyrings/thorio-personal-repo.gpg
```

Add the repository:

```bash
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/thorio-personal-repo.gpg] https://thorio.github.io/apt/debian generic main" | sudo tee /etc/apt/sources.list.d/thorio-personal-repo.list > /dev/null
```

## Maintaining

Add package:

```bash
reprepro includedeb generic package.deb
```

Remove Package:

```bash
reprepro remove generic package
```

## Sources

| package | source |
| ------- | ------ |
| blent | https://github.com/thorio/blent/releases/latest |
| gravel | https://github.com/thorio/gravel/releases/latest |
| rism | https://github.com/thorio/rism/releases/latest |
| rolr | https://github.com/thorio/rolr/releases/latest |
