# DITA CSS Documentation Projects

This repo contains documentation related to writing grid layouts in HTML and CSS. The documentation is written in DITA (Darwin Information Type Architecture) and serves as an example repo for my ENG 517 - Advanced Technical Writing, Editing, and Design course at North Carolina State University.

## Building Outputs with Github Actions

This repo uses Github Actions to create outputs. Refer to the following for details: 

- [.github/workflows/dita-ot-build-actions.yaml](.github/workflows/dita-ot-build-actions.yaml)
- [DITA User Docs - Using Github Actions](https://www.dita-ot.org/dev/topics/using-github-actions)
- [DITA Example YAML files](https://github.com/dita-ot/docs/blob/develop/samples/github-actions/build-using-a-project-file.yaml)

## Building Outputs Manually with the Command Line

See the DITA-OT user guide about how to generate output: [http://www.dita-ot.org/2.1/getting-started/using-dita-command.html](http://www.dita-ot.org/2.1/getting-started/using-dita-command.html)

### Sample DITA Commands

**Command for <code>dita</code> command help**:

<pre>
username@computername:~/dita-ot-2.1.1$ dita --help
</pre>

<pre>
/* DITA options and arguments */

-f == dita output format
-i == dita input map file
-o == dita output directory
-D&lt;property&gt;=&lt;value&gt; == add custom args
    with particular values to dita transformation
-filter &lt;file&gt; == filter and flagging file
</pre>

**Create an HTML5 site**:

<pre>
dita -f html5 -i 'url/to/your/wanted.ditamap' \
  -o 'url/to/your/output/folder' \
</pre>

**Create an HTML5 site with a custom CSS file**:

<pre>
dita -f html5 -i 'url/to/your/wanted.ditamap' \
  -o 'url/to/your/output/folder' \
  -Dargs.cssroot='url/to/your/assets/folder' \
  -Dargs.css='${cssroot}/your-custom-css-file.css' \
  -Dargs.csspath='css' \
  -Dargs.copycss='yes'
</pre>

**Create a PDF**:

<pre>
dita -f pdf -i 'url/to/your/wanted.ditamap' \
  -o 'url/to/your/output/folder' \
</pre>
