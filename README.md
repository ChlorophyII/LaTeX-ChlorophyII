This is ChlorophyII's TeX package. More details will be added later. 

## Highlights
1. Zenburn mode: Add `\zenburn` somewhere before `\begin{document}`. Compile. Protect your eyes.
2. Autobraces: Try `\abra{\abra{\abra{1+1}^{p+1}}+\frac{\pi^2}{6}}`. It will automatically increase its size depending on its contents.  
	However, `\abra{\abra{1+1}+1}` does not look good, for the outer braces  are as small as the inner ones. In that case, use `\abra[big]{\abra{1+1}+1}` instead. *big* can be replaced by *Big*, *bigg* and *Bigg*.
3. Autobrackets: `\abrc`. Usage is the same as `\abra`

## Installing
### macOS
```
> cd ~/Library
> mkdir -p texmf/tex/latex
> cd texmf/tex/latex
> git clone https://github.com/ChlorophyII/LaTeX-ChlorophyII.git
> cd ../..
> texhash
```
Haven't install git?

```
> /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
> brew install git
```

### Other systems
Look at [this question](https://tex.stackexchange.com/questions/1137/where-do-i-place-my-own-sty-or-cls-files-to-make-them-available-to-all-my-te) on TeX exchange.
