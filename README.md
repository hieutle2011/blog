### How to run project

- Install [Hugo][hugo]

- Install theme beautifulhugo [here][theme]

```
cd themes
git ls-files --stage
git rm --cached beautifulhugo && rm -rf beautifulhugo
git submodule add https://github.com/halogenica/beautifulhugo.git beautifulhugo
```

- Add submodule for public

```
cd ..
git ls-files --stage
git rm --cached public && rm -rf public
git submodule add https://github.com/hieutle2011/hieutle2011.github.io.git public
```

- Run script to deploy

```
zsh ./deploy.sh
```

- Troubleshoot with add submodule [here][sub]

### Generate file

- Install [pandoc][pandoc] and TeX Live. Generate html

```
pandoc content/page/cv.md -f markdown -t html -s -o cv.html
```

- If we want PDF file ([TeX Live][texlive] need to be installed)

```
pandoc content/page/cv.md -s -o cv-hieutrungle.pdf
```

[hugo]:https://github.com/gohugoio/hugo/releases
[theme]:https://themes.gohugo.io/beautifulhugo/
[sub]:https://stackoverflow.com/questions/12898278/issue-with-adding-common-code-as-git-submodule-already-exists-in-the-index#12902857
[export]:https://discourse.gohugo.io/t/export-a-resume-as-a-pdf/4138/1
[pandoc]:https://pandoc.org/getting-started.html
[texlive]:https://www.tug.org/texlive/debian.html
[latex]:https://eankeen.github.io/blog/posts/render-latex-with-katex-in-hugo-blog/