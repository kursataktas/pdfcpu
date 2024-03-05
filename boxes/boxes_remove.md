---
layout: default
---

# Remove Boxes

* This command removes selected page boundaries for selected pages.

* Media Box can't be removed since it is mandatory and may be inherited.

* Media Box is mandatory and serves as default/parent box for Crop Box.

* Crop Box serves as default/parent box for Art Box, Bleed Box and Trim Box.

Have a look at some [examples](#examples).

## Usage

```
pdfcpu boxes remove [-p(ages) selectedPages] -- boxTypes inFile [outFile]
```

<br>

### Flags

| name                                         | description    | required
|:---------------------------------------------|:---------------|---------
| [p(ages)](../getting_started/page_selection) | selected pages | no

<br>

### Common Flags

| name                                            | description     | values
|:------------------------------------------------|:----------------|:-------
| [v(erbose)](../getting_started/common_flags.md) | turn on logging |
| [vv](../getting_started/common_flags.md)        | verbose logging |
| [q(uiet)](../getting_started/common_flags.md)   | quiet mode      |
| [u(nit)](../getting_started/common_flags.md)    | display unit    | po(ints),in(ches),cm,mm
| [c(onf)](../getting_started/common_flags.md)       | config dir      | $path, disable
| [upw](../getting_started/common_flags.md)          | user password   |
| [opw](../getting_started/common_flags.md)          | owner password  |

<br>

### Arguments

| name         | description         | required
|:-------------|:--------------------|:--------
| boxTypes     | comma separated list of box types: c(rop), t(rim), b(leed), a(rt)      | yes
| inFile       | PDF input file      | yes
| outFile      | PDF output file     | no

<br>

## Examples

 Remove all page boundaries other than Media Box for page 2 of in.pdf:

```
$ pdfcpu box rem -pages 2 -- "c,b,a,t" in.pdf out.pdf
removing cropBox, trimBox, bleedBox, artBox for in.pdf
writing out.pdf...
```

<br>

Remove Crop Box for all pages of in.pdf:

```
$ pdfcpu box rem -- "crop" in.pdf out.pdf
removing cropBox for in.pdf
writing out.pdf...
pages: all
```