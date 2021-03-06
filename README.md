# Resume Builder
## Installation

> All the instructions are on MacOS Catalina 10.15.7

1. First install Tex on your local machine. There are various versions. I went with the very basic (and relatively small, about 110 MB) BasicTeX - http://www.tug.org/mactex/morepackages.html This will install all standard tools of TeX, LaTeX, pdfTeX, MetaFont, dvips, MetaPost, and XeTeX. The one that we are interested in is XeTeX.

    ```
    $ which xetex
    /Library/TeX/texbin/xetex
    ```

    **Note**: Alternative installation with brew that I have not tried but for your reference - https://tex.stackexchange.com/questions/307483/setting-up-basictex-homebrew

2. When you have successfully installed BasicTex and verified, a utility tool called `tlmgr` gets installed as well. This is the Tex Live Package Manager. It allows us to install all the required packages for the Tex template.


    ```
    $ sudo tlmgr update --self
    $ sudo tlmgr install collection-fontsrecommended titlesec mdframed zref-abspage enumitem sectsty fullpage contour fontawesome5 xcharter
    ```
3. Install `pandoc`
    ```
    $ brew install pandoc
    ```

## Usage
After you have modified the content in `resume.md`, your resume can be generated by running the following command - 
```
$ pandoc -s resume.md --template template.tex  --pdf-engine=xelatex -o resume.pdf
```