# Project Gutenberg Corpora, Translated by Google

This directory contains texts from Project Gutenberg as well as translations of those texts into various languages.

The texts are translated by Google.

For more information on Project Gutenberg, see: https://www.gutenberg.org/

## Directory Structure

The subdirectories here each contain a book from Project Gutenberg, including the source text in EPUB format and the output text, as follows:

- `Author-ID/`
    - `in/` = the extracted EPUB file
    - `out/google/{format}/{langid}/{filename}` = individual files from the EPUB translated by Google

The following formats are available:

- `html`: HTML markup that retains paragraphs, inline styles such as italics, headings, et cetera.
- `txt`: Paragraphs of the HTML with all tags stripped out.
- `breakpoints`: Sentences with breakpoints between wordlike tokens indicated with pipe characters `|`.

Note that `txt` contains paragraphs (derived from HTML) whereas `breakpoints` contains sentences (derived from the machine translation model). The sentences might also include translatable content that was not HTML text content, such as `title` attributes.

The breakpoints are the same as those of the transliteration on translate.google.com. For example, translating the text [The quick brown fox jumps over the lazy dog](https://translate.google.com/?sl=en&tl=th&text=The%20quick%20brown%20fox%20jumps%20over%20the%20lazy%20dog.&op=translate) into Thai produces the following output:

> สุนัขจิ้งจอกสีน้ำตาลกระโดดข้ามสุนัขขี้เกียจอย่างรวดเร็ว
> S̄unạk̄h cîngcxk s̄ī n̂ảtāl kradod k̄ĥām s̄unạk̄h k̄hī̂ keīyc xỳāng rwdrĕw

The corresponding entry in `out/google/breakpoints/th/filename.txt` would contain:

> สุนัข|จิ้งจอก|สี|น้ำตาล|กระโดด|ข้าม|สุนัข|ขี้|เกียจ|อย่าง|รวดเร็ว

The pipe symbols correspond to the spaces in the transliteration.
