# Starting a document

## Start of lab report

<pre><code>\documentclass[11pt]{article}

\usepackage[utf8]{inputenc}
\usepackage[margin=1in]{geometry}
\usepackage[bottom]{footmisc}

\usepackage{fancyhdr, amsmath, setspace, graphicx, float, wrapfig, caption, subcaption, tikz, gnuplottex}

\doublespacing

\pagestyle{fancy}
\lhead{}
\rhead{}

%------------------------------------------
%------------------------------------------

\begin{document}
</code></pre>



## Start of resume

<pre><code>\documentclass[10pt]{article}

%-------------------------------------------
%***Packages***
\usepackage{datetime, fancyhdr, multirow, hyperref, lastpage, multirow, tabularx, textcomp}
\usepackage[left=0.4in, right=0.7in, top=0.7in, bottom=0.6in, headheight=-0.1in]{geometry}
\usepackage[bottom]{footmisc}

%------------------------------------------
%***Spacing commands***
\newcommand{\mysec}[1]{ \vspace{1mm} \large { \textbf{ \textsc{ #1 } } } \vspace{-1mm} }
\setlength{\parindent}{0pt}

\newcommand{\itemizeouter}{\begin{itemize} \setlength{\itemsep}{0mm}}
\newcommand{\itemizeouterend}{\end{itemize}}

\newcommand{\itemizeinner}{\vspace{-2.5mm} \begin{itemize} \setlength{\itemsep}{0mm}}
\newcommand{\itemizeinnerend}{\end{itemize} \vspace{-1mm}}

%------------------------------------------
%***Header***
\pagestyle{fancy}
\renewcommand{\headrulewidth}{0pt}
%\fancyhf{}
\renewcommand*\footnoterule{}

\fancyhead[L]{\hspace{2.15mm} \small NAME}
\fancyhead[R]{\hspace{2.15mm} \small Page 2}
\fancyfoot{}
\fancypagestyle{plain}{ \fancyhf{} }
\pagestyle{fancy}

%------------------------------------------
%------------------------------------------

\begin{document}
</code></pre>


# Figures

## Figure wrapping

<pre><code>\begin{wrapfigure}{r}{0.5\textwidth}
    \centering
    \includegraphics[width=0.48\textwidth]{soleil_schematic.png}
    \caption{The structure of a Soleil compensator. (Figure from the ``Babinet–Soleil\_compensator'' Wikipedia page.)}
\end{wrapfigure}
</code></pre>


<pre><code>\begin{figure}[H]
    \centering
    \includegraphics[width=\textwidth]{1schematic_pockels.jpg}
    \caption{Experimental setup for characterizing the Pockels cell.  The dashed (red) lines with arrows are the path of the laser beam, and the dotted (green) lines are cables connecting the various devices.  The gaps indicate where more components will be added to the system in later parts of the experiment.}
    \label{1schematic_pockels}
\end{figure}

\begin{figure}[H]
    \centering
    \includegraphics[width=\textwidth]{pockels_cell.jpg}
    \caption{Output detector voltage vs.\ input amplifier DC voltage for the Pockels cell oriented at 320$^o$ (a location of minimum transmission).  A best-fit to the data was found using Excel's Solver.}
    \label{pockels_cell_data}
\end{figure}
</code></pre>


## Subfigures

<pre><code>\begin{figure}[H]
        \centering
        \begin{subfigure}[b]{0.4\textwidth}
                \includegraphics[width=\textwidth]{soleil__2x_freq_sine.jpg}
                \caption{Sine wave input.}
                \label{Sine_wave_input}
        \end{subfigure}
        ~
        \begin{subfigure}[b]{0.4\textwidth}
                \includegraphics[width=\textwidth]{soleil__2x_freq_square.jpg}
                \caption{Sawtooth wave input.}
                \label{Sawtooth_wave_input}
        \end{subfigure}
        \caption{The output frequency (top) at twice the input driving frequency (bottom).}
        \label{soleil__2x_freq}
\end{figure}
</code></pre>



## Minipage (i.e. for precisely positioning text around a figure)

<pre><code>\begin{minipage}[c]{0.5\textwidth}
    \includegraphics[width=0.95\textwidth]{pockels_45deg2.jpg}
    \captionof{figure}{An oscilloscope output (top) for the Pockels cell with the beam chopper on.}
    \label{pockels45deg2}
\end{minipage}
\begin{minipage}[c]{0.45\textwidth}
    When the battery was disconnected, the response of the diode decreased significantly, and it was not possible to see the RF signal emitted by the laser.  The initial photodiode was exchanged for another before the complete setup with the TV worked and the laser RF signal could be measured.  The first photodiode performed poorly at high frequencies, because the battery was likely low.
\end{minipage}
</code></pre>
