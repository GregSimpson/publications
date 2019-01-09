\documentclass{article}
\usepackage{amsmath}% http://ctan.org/pkg/amsmath
\usepackage{kbordermatrix}% http://www.hss.caltech.edu/~kcb/TeX/kbordermatrix.sty
\usepackage{blkarray}% http://ctan.org/pkg/blkarray
\usepackage{hyperref}
\usepackage{blindtext}
\usepackage{enumitem}
\usepackage{listings}
\usepackage{xcolor}
\begin{document}

\centerline{\sc \large Matrix Math for Data Science }
\vspace{.5pc}
\centerline{\sc Part 1 - Addition and Subtraction}
\centerline{\it (GregSimpson 2018, December)}
\vspace{2pc}


\section{Introduction and Rationale}
I recently returned to graduate school as a "seasoned computer professional".  I was looking to update my skills and fill in the gaps in my data science knowledge. 
I applied and was accepted into the University of Denver's MS in Data Science program.
\\
\\
One of the fundamental topics in data science is math. So the university has a few "bridge" classes to refresh and sharpen your math skills.
My first class this past semester was Discrete Math and Linear Algebra.  I will save the discrete math topic for a different series on another day.
For this series, I will discuss matrix math with a little linear algebra mixed in.
\\
\\
There are lots of articles available that discuss the reasons for using various mathematical algorithms.  In an effort to not add to that pile of material, I will focus on the mechanics of how you go about applying some techniques.  My examples will start out pretty simple and try not to get too complex.   I intend this to be digestible by beginners in the field.
We'll see how it goes.
\\
\\
 Please feel free to leave feedback.
\\
\vspace{3pc}

\section{Definitions}
We will start with a few definitions related to matrices.  It helps if you think of them like database tables, so I will use database table imagry in my explanations.
\\
\begin{description}
\item [columns] the fields that define a table; they go left to right, horizontally
\[
\begin{array}{lc}
 \verb|example of columns| & \kbordermatrix{\text{columns}&col_1&col_2&\ldots &col_n\cr
                rows& \vdots & \vdots & \ddots & \vdots\cr
               } \\[15pt]
\end{array}
\]

\item [rows] the data that populates the table; each row usually has an entry for each column
\[
\begin{array}{lc}
 \verb|example of rows| & \kbordermatrix{&col_1&col_2&\ldots &col_n\cr
	     row_1&\vdots &  \vdots  & \ldots & \vdots\cr
                row_2& \vdots  &  \vdots & \ldots & \vdots\cr	
                row_m& \vdots & \vdots & \ldots & \vdots\cr
               } \\[15pt]
\end{array}
\]
\item [dimension] numeric description of the number of rows and columns; in math problems, they usually say an "m by n" matrix or "m x n" \\where m = rows and n = columns
\[
\begin{array}{lc}
  \verb|3x3 : m=3, n=3| & \begin{bmatrix}
                    a & b & c \\
                    d & e & f \\
                    g & h & i
                  \end{bmatrix} \\[15pt]
\\
  \verb|2x3 : rows=2, cols=3| & \begin{bmatrix}
                    a & b & c \\
 