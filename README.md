This is ChlorophyII's LaTeX package. More details will be added later. 

`\usepackage{ChlorophyII}`

## Highlights
1. Zenburn mode: Add `\zenburn` somewhere before `\begin{document}`. Compile. Protect your eyes.
2. Auto-brackets: Try `\abrr{\abrr{\abrr{1+1}^{p+1}}+\frac{/pi^2}{6}}`. It will automatically increase its size depending on its contents.  
	However, `\abrr{\abrr{1+1}+1}` does not look good, for the outer braces  are as small as the inner ones. In that case, use `\abrr[big]{\abrr{1+1}+1}` instead. *big* can be replaced by *normal*, *Big*, *bigg* and *Bigg*.  
	`\abrs` and `\abrc` work exactly the same way as `\abrr`, except that they give square and curly brackets respectively.  
3. Finite-series: `\series` generates the expanded form of the finite sum of a series from its expression of the nth-term. It liberates you from repeatedly typing awkward LaTeX expressions. Look at it!  
	<p align="center"><img src="readme-images/series_j_frac_n^.pdf"></p>
	Instead of `\frac{1^{-p}}{2^{-1}}+\frac{2^{-p}}{2^{-2}}+\cdots+\frac{j^{-p}}{2^{-j}}`, you just need `\series[j]{\frac{\n^{-p}}{2^{-\n}}}`. Fewer characters are good, but the real power of `\series` unfolds when you want to change the term a little bit. Say, if you want to associate `p` with an index, you can simply replace `p` by `p_\n`. 
	See [examples](#examples) for more information.

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

## <a name="examples"></a>Examples
1. `\NN, \ZZ, \QQ, \RR, \CC`  
	<p align="center"><img src="readme-images/NN,_ZZ,_QQ,_RR,_.pdf"></p>
2. `\Re{z}, \Im{z}`  
	<p align="center"><img src="readme-images/Re_z_,_Im_z.pdf"></p>
3. `\abs{x-y},\norm{f-g}`  
	<p align="center"><img src="readme-images/abs_x-y_,_norm_f.pdf"></p>
4. Auto-brackets:  
	It is convenient to use `\abrr`, `\abrs` and `\abrc` in a lot of situations. It helps you easily adjust the size of brackets and gives your code better structure.  
	`\abrr{\abrr{\abrr{1+1}^{p+1}}+\frac{/pi^2}{6}}`  
	<p align="center"><img src="readme-images/abra_abra_abra_1.pdf"></p>  
	`\abrr{\abrr{1+1}+1}` produces bad typesetting  
	<p align="center"><img src="readme-images/abra_abra_1+1_+1.pdf"></p>  
	`\abrr` can take one argument like `\abrr[big]{\abrr{1+1}+1}`  
	<p align="center"><img src="readme-images/abra_big_abra_1+.pdf"></p>  
	*big* can be replaced by *normal*, *Big*, *bigg* or *Bigg*.  
	`\abrs` and `\abrc` work exactly the same way as `\abrr`, except that they give square and curly brackets respectively.  
	`\abrc[Big]{a\in\RR:\abrs{\sin\abrr[normal]{x+x^2}}_0^a\ge0}`  
	<p align="center"><img src="readme-images/abrc_Big_a_in_RR.pdf"></p>  
5. Finite-series:  
	It takes three optional and one required arguments. The syntax is  
	`\series[index][starting index][delimiter]{general term}`.  
	By default, *index* is n, *starting index* is 1, and *delimiter* is +. Optional arguments must be input in order. If you want to change the delimiter, you must type in *index* and *starting index*. *starting index* can be either 1 or 0. In *general term*, `\n` is used as a placeholder for the index.  
	
	`\series{a_\n}`  
	<p align="center"><img src="readme-images/series_a_n.pdf"></p>  
	`\series[j]{\frac{\n^{-p}}{2^{-\n}}}`
	<p align="center"><img src="readme-images/series_j_frac_n^.pdf"></p>  
	`\series[m][0]{x_\n}`  
	<p align="center"><img src="readme-images/series_m_0_x_n.pdf"></p>  
	`a=\series[k][0][,]{c_\n}=b`  
	<p align="center"><img src="readme-images/a=_series_k_0_,_.pdf"></p>  
	`\series[n][1][,]{\n}`  
	<p align="center"><img src="readme-images/series_n_1_,_n.pdf"></p>  
6. Theorems, definitions and remarks:  
	*definition*, *lemma*, *proposition*, *theorem*, *corollary*, *conjecture*, *example*, *remark*, *note* and *fact* are environments, and they are used in the same way. You may or may not give a name to the theorem or definition or...

	```tex
	\begin{theorem}[Fermat's Last Theorem]
	No three positive integers $a$, $b$, and $c$ satisfy the equation $a_n+b_n=c_n$ for any integer value of $n$ greater than $2$.
	\end{theorem}
	```
	<p align="center"><img src="readme-images/Fermat's_Last_Th.pdf"></p>  