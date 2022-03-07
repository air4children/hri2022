# arXiv submission
## Preparation
1. Edit paths in A_copy-tex-figures.bash

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
bash ../B_pdflatex-bibtex.bash
```
Check that reference were appropietely called `evince main.pdf`

4.1 edit reference section as follows
```
%%\bibliography{../references/references}
\input{main.bbl} %% uncomment for arxiv version
```

4.2 compile `main.tex`
```
cd files/
bash ../C_pdflatex-pdflatex.bash
```

4.3 check pdf 
```
cd files/
evince main.pdf
```

4.4 clean project 
```
cd files/
bash ../D_clean-tex-project.bash
```

5. compress it as zip 
```
bash E_zip_files.bash v00
```

:tada: zip is ready to be submitted in arXiv


## Submission

1. Go to arxiv and submit the above zip file with title, author list, and abstract.

See [Submission Log](SubmissionLog.md) for further deteails.
