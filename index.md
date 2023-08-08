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

This contains mostly other people's software that's not available in the standard repos.

**You probably shouldn't use this.**

* * *

## Installation

Install requisite packages:

```bash
apt-get update
apt-get install apt-transport-https ca-certificates curl gnupg
```

Add the gpg key:

```bash
curl -fsSL https://thorio.github.io/apt/gpg | sudo gpg --dearmor -o /usr/share/keyrings/thorio-personal-repo-keyring.gpg
```

Add the repository:

- Ubuntu

	```bash
	echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/thorio-personal-repo-keyring.gpg] https://thorio.github.io/apt/ubuntu generic main" | sudo tee /etc/apt/sources.list.d/thorio-personal-repo.list > /dev/null
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
| alacritty | https://launchpad.net/~aslatter/+archive/ubuntu/ppa |
| blent | https://github.com/thorio/blent/releases/latest |
| code | https://code.visualstudio.com/docs/setup/linux |
| espanso | https://github.com/federico-terzi/espanso/releases/latest |
| libinput-gestures | https://github.com/thorio/libinput-gestures |
| plexamp | https://plexamp.com/#downloads |
| sunset-cursor-theme | https://github.com/thorio/packaging/tree/master/sunset-cursor-theme |
