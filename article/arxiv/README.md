# arXiv submission
## Preparation
1. Edit paths in A_copy-tex-figures.sh

2. Run script to copy tex files and images to arxiv/files path
```
bash A_copy-tex-figures.bash
```

3. edit paths for figures in `file\main.tex` as follows
```
%\graphicspath{{../figures}} %goes to path: figures/
\includegraphics[width=\textwidth]{drawing-v01.png}
\includegraphics[width=\linewidth]{drawing-v00.png}
\bibliography{../../references/references}
```

4. compile `main.tex` file
```
cd files/
sh ../B_pdflatex-bibtex.sh
```
3.1 edit reference section as follows
```
%%\bibliography{../references/references}
\input{main.bbl} %% uncomment for arxiv version
```

3.2 compile `main.tex`
```
cd files/
sh ../C_pdflatex-pdflatex.sh
```

3.3 check pdf 
```
cd files/
evince main.pdf
```

3.4 clean project 
```
cd files/
sh ../D_clean-tex-project.sh
```

4. compress it as zip 
```
sh E_zip_files.sh v01
```

:tada: zip is ready to be submitted in arXiv


## Submission
Login to arXiv and submit the above zip file
See [Submission Log](SubmissionLog.md) for further deteails.