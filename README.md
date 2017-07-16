# The `kdp` LaTeX document class

This is a simple reimplementation of the LaTeX `book` class for use with the common [Amazon KDP print beta and CreateSpace paperback sizes](https://kdp.amazon.com/en_US/help/topic/A2BXOVPUCZ09J8).

The PDFs required by KDP/CS are unusual in that the page size required is the final trim size. This is so their printing equipment can place the pages onto the physical sheets of paper that are fed into the printer. While this saves the intrepid self-publisher from having to worry about pre-press matters, it also means that page sizes must be specified manually.

While not difficult, having the page size defined in the options to a package like `geometry` introduces the chance of an error creeping in. This class solves that problem by providing presets that take the guesswork out of setting up the page size.

The following options are available:

|       Option| Size          |
|------------:|:--------------|
|     500paper| 5" x 8"       |
|     506paper| 5.06" x 7.81" |
|     525paper| 5.25" x 8"    |
|     550paper| 5.5" x 8.5"   |
|     600paper| 6" x 9"       |
|     614paper| 6.14" x 9.21" |
|     669paper| 6.69" x 9.61" |
|     700paper| 7" x 10"      |
|     744paper| 7.44" x 9.69" |
|     750paper| 7.5" x 9.25"  |
|     800paper| 8" x 10"      |
|  letterpaper| 8.5" x 11"    |
|     825paper| 8.25" x 6"    |
|    825Spaper| 8.25" x 8.25" |
|    850Spaper| 8.5" x 8.5"   |

As a mnemonic, the page sizes are named after the page width carried out to two decimal points. The square pages also have an "S" after the number.

## Usage

Simply add the desired page size to the class options as you would with any other paper size. The 6x9 size is the default, other sizes are chosen like so:

```tex
    \documentclass{kdp} % 6"x9"
```

```tex
    \documentclass[500paper]{kdp} % 5"x8"
```

Any other options can be used normally (i.e. `11pt` or `openany`).

## Installation

Place the `kdp.cls` file in the folder where your main `.tex` file is and it will be found. The more abitious can place it in their `$TEXMFHOME` folder (usually `/home/<user>/texmf/tex`).

## Notes

The paper will remain at the default size (letter/A4) when displaying the PDF. Add the `geometry` package to have the PDF "trimmed" to the right size. This is also a good idea as it makes setting margins easy (the default LaTeX margins don't work well at paperback sizes). If your book requires extra width for full-page bleeds, consult the [guide](https://images-na.ssl-images-amazon.com/images/G/01/00/01/00/02/17/60/10002176030.pdf) to set the page size.

See the [MWE file](https://github.com/JenniferMack/latex-kdp/blob/master/kdp.tex) to get started. It also shows how to use the `geometry` package with the most recent LuaLaTeX (TeXLive 2017).

