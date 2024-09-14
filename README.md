# testing

### Bash

### let`s Git Started

```sh
# Change directory
cd ~/path/to/repo       

# List files in the directory
ls                                    

# Display the status of the repository
git status

# Stage all changed files for the next commit
git add .

# Take a snapshot and store it in the log with a comment
git commit -m 'Comment'  

# List the repository aliases on your machine and on GitHub (default are master and origin)
git remote -v

# Pull changes from origin (alias of the repo on GitHub) to master (alias of the repo on your machine)
git pull origin master 

# Push changes from master (alias of the repo on your machine) to origin (alias of the repo on GitHub)
git push origin master

# List local branches (Check the current branch)
git branch

# List all remote branches
git branch -r

# List both local and remote branches
git branch -a

# Switch to a different branch
git checkout branch/name
  
# Checkout a specific commit by its identifier
git checkout num-del-commit

# Return to the most recent commit on the master branch
git checkout master

# List commits in a shortened format
git log --pretty=oneline --abbrev-commit

# Undo all commits after [commit], preserving changes locally
git reset [commit]

# Discard all history and changes back to the specified commit
git reset --hard [commit]
git reset --hard

# Force a push (useful when a local commit is deleted)
### Refer to: https://7sabores.com/blog/como-revertir-un-push-git
git push origin +master
git push --force

# Remove a file (e.g., rm data.tmp)
rm [file]   

# Remove a file with confirmation
rm -i [file]

# Open the directory in Finder
open .

# Clear the terminal
command+K
```

### bib-tidy

```sh
# Install bibtex-tidy globally using npm
npm install -g bibtex-tidy

# To format a .bib file
bibtex-tidy references.bib

# To remove the url parametrer
bibtex-tidy --omit=url references.bib

# Enclose all property values in braces
bibtex-tidy --curly references.bib

# Strip quotes and braces from numeric/month values
bibtex-tidy --numeric references.bib

# Convert all months to three letter abbreviations
bibtex-tidy --months references.bib

# Indent all fields with the specified number of spaces
bibtex-tidy --space=4 references.bib

# Indent all fields with a tab
bibtex-tidy --tab references.bib

# Insert whitespace between fields and values so that values are visually aligned
bibtex-tidy --align=14 references.bib

# Sort entries by the specified field names
bibtex-tidy --sort references.bib
--sort (sort by citation key)
--sort=-year,name (sort year descending then name ascending)
--sort=name,year

# Where values are all caps, make them title case
bibtex-tidy --drop-all-caps references.bib

# Where an entire value is enclosed in double braces, remove the extra braces
bibtex-tidy --strip-enclosing-braces references.bib

# Use
bibtex-tidy --curly --numeric --months --space=4 --tab --strip-enclosing-braces --sort --drop-all-caps file.bib

bibtex-tidy --curly --numeric --months --space=4 --tab --strip-enclosing-braces --sort --drop-all-caps file.bib

bibtex-tidy --curly --numeric --months --modify --space=4 --tab --strip-enclosing-braces --sort=key --duplicates=doi --omit=abstract,keywords --drop-all-caps --sort-fields=author,title,year --remove-empty-fields --escape --encode-urls file.bib
```

### pre-commit

```sh
# Install the pre-commit package using pip
pip install pre-commit

# Display the installed version of pre-commit
pre-commit --version

# Run all pre-commit hooks on all files in the repository
pre-commit run --all-files

# Perform a full integrity check on the Git repository
git fsck --full`

# Format and indent the LaTeX file, overwriting the original file
latexindent.pl r-packages.tex -o r-packages.tex
```

## LaTex

### thesis template commands

````Tex
% Section formatting

\part{Your Part Title}
\chapter{Your Chapter Title}
\section{Your Section Title}
\subsection{Your Subsection Title}
\subsubsection{Your Subsubsection Title}
\paragraph{Your Paragraph Title}
\subparagraph{Your Subparagraph Title}

% Text size

\Huge
\huge
\LARGE
\Large
\large
\normalsize
\small
\footnotesize
\scriptsize
\tiny

% Font shapes

\emph{} % This is Italic Shape
\scshape{} % This is Small Caps Shape

% New thought block

\newthought{Your new thought here} 

% Analytical Index entries

\analyticentry{Your Index Term 1}
\analytics{Your Index Term 1}

% Label and References

\hyperref[tab:figura1]{Figura \ref{fig:figura1}}

\label{tab:tabla1} % Table reference
\label{apendiceA} % Appendices references
\label{introduction} % Chapter reference

% Center environment

\begin{center}
  Your centered content goes here
\end{center}

% Itemize and enumerate environments

\begin{itemize}
  \item Your item 1
  \item Your item 2
\end{itemize}

\begin{enumerate}
  \item Your item 1
  \item Your item 2
\end{enumerate}

% Quote Environment

\begin{quote}
  \lipsum[2]
\end{quote}

% Savequote environment

\begin{savequote}[85mm]
  \small{Your quote here.}
  \qauthor{Your Author}
\end{savequote}

% Equation Environment

\begin{equation}
x = 1
\end{equation}

% Figure Environment

\begin{figure}[H]
    \centering 
        \includegraphics[width = \textwidth]{figures/fig#}
        \caption[Lorem Ipsum]{Proin at eros...
    \label{fig:figura#}}
\end{figure}

% Full page figure Environment

\newpage
\thispagestyle{empty}
\begin{landscape}
\thispagestyle{empty}
  \begin{figure}[p]
    \centering
    \includegraphics[width = \linewidth, keepaspectratio]{figures/fig#.png}
    \caption[Lorem Ipsum]{Proin at eros...}
    \label{fig:figura#}
  \end{figure}
\end{landscape}

% Code Listing Environment

\begin{lstlisting}[language = R, caption = Lorem Ipsum]
    Lorem Ipsum
\end{lstlisting}

% Footnotes

\footnote{Lorem ipsum.}\textsuperscript{,}\footnote{Lorem ipsum.}

\footnote{\lipsum[8]}

% References

% The references.bib file contains the references. By default, the references are cited in the APSA style. 
% Use the command \citep{} to manage the references.

\citep{BibTeX key, BibTeX key}

\citep[pg.~32]{BibTeX key}

\citep{BibTeX key}

\citep[\emph{véase}][pg.~5]{BibTeX key}

\citep[Chap.~5]{BibTeX key}

% Page settings

\blankpage % Add a blank page
\newpage % Add a new page
