---
title: Notes Index
description: Notes Index
permalink: /notes/
lastmod: '2021-11-10T04:23:57.881Z'
---

# Quick Start

https://www.bls.gov/oes/current/oes113021.htm#st

## [Getting Started](/notes/getting-started)

[Devops](https://docs.gitlab.com/ee/topics/autodevops/stages.html)

### Windows

Open Powershell in Admin mode

```shell
powershell -Command "Start-Process PowerShell -Verb RunAs"
```

Set the following environment variables:

```powershell

  $envName= 'psgist'
  $envValue= '64e4d4d22d4757be6e8e26fd39d760c9'
  $env:psgist = $envValue

function Set-EnvVar($envName, $envValue) {
    # param($envName, $envValue)
    # $env:$name = $value

[System.Environment]::    ($envName, $envValue,[System.EnvironmentVariableTarget]::User)
write-host 'Environment variable set'
write-host '$envName: $envValue'
}

Set-EnvVar $envName $envValue

echo $env:psgist


```


```powershell
$name = "amr"
$value = "smells"

function Set-LocalVar($name, $value) {
    # parm($name, $value)
    write-host "$name $value"
}

Set-LocalVar amr smells


```




[Check-Get-PS-Profile.ps1]() 

Navigate to Profile home directory

```powershell
split-path $PROFILE | cd
```
### Download $Profile

```powershell

function Git-profile {
  $gitUser ="bamr87"
  Write-Output $env:psgist
  $masterProfile = "Microsoft.PowerShell_profile.ps1"
  
  $url = "https://gist.githubusercontent.com/$gitUser/$env:psgist/raw/$masterProfile"
  $FileName = Split-Path $profile -Leaf
  $FilePath = Split-Path $profile
  $FullPath = "$FilePath\$FileName"
  
  $webclient = New-Object System.Net.WebClient
  $webclient.DownloadFile($url,$FullPath)
}

function Restart-Powershell {
  Start-Process powershell
  exit
}

```
restart  powershell function
```powershell
function Restart-Powershell {
  Start-Process powershell
  exit
}
```

### Linux


### MacOS

[Importing and exporting homebrew packages](https://tomlankhorst.nl/brew-bundle-restore-backup/)

```javascript
document.write('Hello, world!');
```


```powershell
vscode://file/C:/Users/AmrAbdel-Motaleb/OneDrive/Documents/GitHub/{{ page.path}}
```
```bash
code $HOME/Github/
```

```liquid
{% raw %}
{{site.github.repository_url}}
{% endraw %}
```

```html
{%raw %}
<div class="sidebar__top">
  <a href="'''liquid{{site.github.repository_url}}'''/blob/gh-pages/{{page.name}}">
    <i class="fab fa-github-square"></i>
  </a>
  <a href="vscode://file{{ site.local_git_pc}}/{{ site.local_repo }}/{{ page.path }}">
    <i class="fas fa-laptop-code"></i>
  </a>
  <a href="vscode://file{{ site.local_git_mac}}/{{ site.local_repo }}/{{ page.path }}">
    <i class="fas fa-laptop-code"></i>
  </a>
  <a href="#page-title" class="back-to-top">{{ site.data.ui-text[site.locale].back_to_top | default: 'Back to Top' }} &uarr;</a>
</div>
{% endraw %}
```
## Features 

### Hover Notes

![](../assets/images/hover-note.png)

### Paste images in Markdown


![](../assets/images/markdown_paste.gif)


### Autoscale images


### Render LaTeX from markdown

add script to head

```html
<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>
```


```LaTeX
$$ \nabla_\boldsymbol{x} J(\boldsymbol{x}) $$
```
$$ \nabla_\boldsymbol{x} J(\boldsymbol{x}) $$


## Auto Name Code Snippet

```yaml

# Conversion
markdown: kramdown
highlighter: rouge
syntax_highlighter: coderay
# lsi: false
# excerpt_separator: "\n\n"
# incremental: false

# Markdown Processing https://jekyllrb.com/docs/configuration/markdown/
kramdown: # https://kramdown.gettalong.org/options.html
  input: GFM
  header_offset: 2
  # hard_wrap: false
  auto_ids: true
  # footnote_nr: 1
  # entity_output: as_char
  # toc_levels: 1..6
  # smart_quotes: lsquo,rsquo,ldquo,rdquo
  # enable_coderay: false
  ```

### Add [Submodules](http://git-scm.com/book/en/v2/Git-Tools-Submodules) 