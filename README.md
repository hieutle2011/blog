### How to run project

- Install [Hugo][hugo]

- Install theme beautifulhugo [here][theme]

```
cd themes
git ls-files --stage
git rm --cached beautifulhugo
git submodule add https://github.com/halogenica/beautifulhugo.git beautifulhugo
```

- Add submodule for public

```
git ls-files --stage
git rm --cached public
git submodule add https://github.com/hieutle2011/hieutle2011.github.io.git public
```

- Run script to deploy

```
zsh ./deploy.sh
```

- Troubleshoot with add submodule [here][sub]

[hugo]:https://github.com/gohugoio/hugo/releases
[theme]:https://themes.gohugo.io/beautifulhugo/
[sub]:https://stackoverflow.com/questions/12898278/issue-with-adding-common-code-as-git-submodule-already-exists-in-the-index#12902857