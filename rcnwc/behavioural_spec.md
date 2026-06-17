# Behavioural Specification

This file defines the behavioural specification.
It defines the semantics and statistics it supports.
For examples, please refer to [Behavioural Examples](behavioural_spec_examples.md).

## External Standards

### Unicode Code point
  As defined by the [official unicode glossary](https://www.unicode.org/glossary/#code_point).

### Unicode White_Space
  A code point possessing the [White_Space property](https://www.unicode.org/Public/UCD/latest/ucd/PropList.txt) 
  defined by the Unicode Character Database.

 ## RCNWC Terms

### RCNWC Line Separator
  Unicode does not define a dedicated Line_Separator
  property analogous to the White_Space property.

  RCNWC therefore explicitly defines the set of
  recognized line separators as any of the following:
  - U+000A LINE FEED (LF)
  - U+000D CARRIAGE RETURN (CR)
  - U+0085 NEXT LINE (NEL)
  - U+2028 LINE SEPARATOR (LS)
  - U+2029 PARAGRAPH SEPARATOR (PS)

### Character
  A Unicode code point in the input.
  Grapheme clusters are not considered a single
  character.

### Word
  A word is a maximal contiguous sequence of 
  Unicode code points that do not have the 
  Unicode White_Space property.

### Line
  A maximal sequence of Unicode code points 
  separated by Unicode line-separator characters.

## RCNWC Statistics

### Byte Count
  Number of bytes read from the input stream.

### Character Count
  Number of Characters in the input.

### Word Count
  Number of Words in the input.

### Line Count
  Number of Lines in the input.
