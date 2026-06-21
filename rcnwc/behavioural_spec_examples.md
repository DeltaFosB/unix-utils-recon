# Behavioural Examples

## Example 1 : Empty Input

### Input

```text
""
```

### Expected Statistics

| Statistic       | Value |
| --------------- | ----- |
| Byte Count      | 0     |
| Character Count | 0     |
| Word Count      | 0     |
| Line Count      | 1     |

---

## Example 2 : Simple ASCII

### Input

```text
"hello"
```

### Expected Statistics

| Statistic       | Value |
| --------------- | ----- |
| Byte Count      | 5     |
| Character Count | 5     |
| Word Count      | 1     |
| Line Count      | 1     |

---

## Example 3 : Whitespace (Space)

### Input

```text
"hello world"
```

### Expected Statistics

| Statistic       | Value |
| --------------- | ----- |
| Byte Count      | 11     |
| Character Count | 11     |
| Word Count      | 2     |
| Line Count      | 1     |

---

## Example 4 : Whitespace (Tab)

### Input

```text
"hello\tworld"
```

### Expected Statistics

| Statistic       | Value |
| --------------- | ----- |
| Byte Count      | 11     |
| Character Count | 11     |
| Word Count      | 2     |
| Line Count      | 1     |

---

## Example 5 : Whitespace (Newline)

### Input

```text
"hello\nworld"
```

### Expected Statistics

| Statistic       | Value |
| --------------- | ----- |
| Byte Count      | 11     |
| Character Count | 11     |
| Word Count      | 2     |
| Line Count      | 2     |

---

## Example 6 : Whitespace (CRLF)

### Input

```text
"hello\r\nworld"
```

### Code Points

```text
U+000D CARRIAGE RETURN
U+000A LINE FEED
```

### Expected Statistics

| Statistic       | Value |
| --------------- | ----- |
| Byte Count      | 12     |
| Character Count | 12     |
| Word Count      | 12     |
| Line Count      | 2     |

---

## Example 7 : Unicode (Emoji)

### Input

```text
"😀"
```

### Code Points

```text
U+1F600 GRINNING FACE
```

### Expected Statistics

| Statistic       | Value |
| --------------- | ----- |
| Byte Count      | ?     |
| Character Count | ?     |
| Word Count      | ?     |
| Line Count      | ?     |

---

## Example 8 : Unicode (Devanagari)

### Input

```text
"नमस्ते"
```

### Code Points

```text
U+0928 DEVANAGARI LETTER NA
U+092E DEVANAGARI LETTER MA
U+0938 DEVANAGARI LETTER SA
U+094D DEVANAGARI SIGN VIRAMA
U+0924 DEVANAGARI LETTER TA
U+0947 DEVANAGARI VOWEL SIGN E
```

### Expected Statistics

| Statistic       | Value |
| --------------- | ----- |
| Byte Count      | ?     |
| Character Count | ?     |
| Word Count      | ?     |
| Line Count      | ?     |

---

## Example 9 : Unicode (Hanzi)

### Input

```text
"你好"
```

### Code Points

```text
U+4F60 CJK UNIFIED IDEOGRAPH-4F60
U+597D CJK UNIFIED IDEOGRAPH-597D
```

### Expected Statistics

| Statistic       | Value |
| --------------- | ----- |
| Byte Count      | ?     |
| Character Count | ?     |
| Word Count      | ?     |
| Line Count      | ?     |

---

## Example 10 : Grapheme Cluster (Combining Character)

### Input

```text
"é"
```

### Code Points

```text
U+0065 LATIN SMALL LETTER E
U+0301 COMBINING ACUTE ACCENT
```

### Expected Statistics

| Statistic       | Value |
| --------------- | ----- |
| Byte Count      | ?     |
| Character Count | ?     |
| Word Count      | ?     |
| Line Count      | ?     |

### Explanation

```text
Although visually rendered as a single glyph,
RCNWC counts Unicode code points rather than
grapheme clusters.
```

---

## Example 11 : Grapheme Cluster (Flag Emoji)

### Input

```text
"🇮🇳"
```

### Code Points

```text
U+1F1EE REGIONAL INDICATOR SYMBOL LETTER I
U+1F1F3 REGIONAL INDICATOR SYMBOL LETTER N
```

### Expected Statistics

| Statistic       | Value |
| --------------- | ----- |
| Byte Count      | ?     |
| Character Count | ?     |
| Word Count      | ?     |
| Line Count      | ?     |

### Explanation

```text
Although rendered as a single flag emoji,
RCNWC counts Unicode code points rather than
grapheme clusters.
```

---

## Example 12 : Line Separator (NEXT LINE)

### Input

```text
"hello<U+0085>world"
```

### Code Points

```text
U+0068 LATIN SMALL LETTER H
U+0065 LATIN SMALL LETTER E
U+006C LATIN SMALL LETTER L
U+006C LATIN SMALL LETTER L
U+006F LATIN SMALL LETTER O
U+0085 NEXT LINE
U+0077 LATIN SMALL LETTER W
U+006F LATIN SMALL LETTER O
U+0072 LATIN SMALL LETTER R
U+006C LATIN SMALL LETTER L
U+0064 LATIN SMALL LETTER D
```

### Expected Statistics

| Statistic       | Value |
| --------------- | ----- |
| Byte Count      | ?     |
| Character Count | ?     |
| Word Count      | ?     |
| Line Count      | ?     |

---

## Example 13 : Line Separator (LINE SEPARATOR)

### Input

```text
"hello<U+2028>world"
```

### Code Points

```text
U+2028 LINE SEPARATOR
```

### Expected Statistics

| Statistic       | Value |
| --------------- | ----- |
| Byte Count      | ?     |
| Character Count | ?     |
| Word Count      | ?     |
| Line Count      | ?     |

---

## Example 14 : Line Separator (PARAGRAPH SEPARATOR)

### Input

```text
"hello<U+2029>world"
```

### Code Points

```text
U+2029 PARAGRAPH SEPARATOR
```

### Expected Statistics

| Statistic       | Value |
| --------------- | ----- |
| Byte Count      | ?     |
| Character Count | ?     |
| Word Count      | ?     |
| Line Count      | ?     |

---

## Example 15 : Pure Whitespace

### Input

```text
" \t\n\r"
```

### Code Points

```text
U+0020 SPACE
U+0009 CHARACTER TABULATION
U+000A LINE FEED
U+000D CARRIAGE RETURN
```

### Expected Statistics

| Statistic       | Value |
| --------------- | ----- |
| Byte Count      | ?     |
| Character Count | ?     |
| Word Count      | ?     |
| Line Count      | ?     |

---

## Example 16 : Mixed ASCII, Unicode and Whitespace

### Input

```text
"hello 😀 world"
```

### Code Points

```text
U+0068 LATIN SMALL LETTER H
U+0065 LATIN SMALL LETTER E
U+006C LATIN SMALL LETTER L
U+006C LATIN SMALL LETTER L
U+006F LATIN SMALL LETTER O
U+0020 SPACE
U+1F600 GRINNING FACE
U+0020 SPACE
U+0077 LATIN SMALL LETTER W
U+006F LATIN SMALL LETTER O
U+0072 LATIN SMALL LETTER R
U+006C LATIN SMALL LETTER L
U+0064 LATIN SMALL LETTER D
```

### Expected Statistics

| Statistic       | Value |
| --------------- | ----- |
| Byte Count      | ?     |
| Character Count | ?     |
| Word Count      | ?     |
| Line Count      | ?     |

---

## Example 17 : Mixed Scripts

### Input

```text
"नमस्ते 世界 😀"
```

### Code Points

```text
U+0928 DEVANAGARI LETTER NA
U+092E DEVANAGARI LETTER MA
U+0938 DEVANAGARI LETTER SA
U+094D DEVANAGARI SIGN VIRAMA
U+0924 DEVANAGARI LETTER TA
U+0947 DEVANAGARI VOWEL SIGN E
U+0020 SPACE
U+4E16 CJK UNIFIED IDEOGRAPH-4E16
U+754C CJK UNIFIED IDEOGRAPH-754C
U+0020 SPACE
U+1F600 GRINNING FACE
```

### Expected Statistics

| Statistic       | Value |
| --------------- | ----- |
| Byte Count      | ?     |
| Character Count | ?     |
| Word Count      | ?     |
| Line Count      | ?     |

---

## Example 18 : Mixed Scripts and Line Separators

### Input

```text
"नमस्ते<U+2028>世界<U+2029>😀"
```

### Code Points

```text
U+2028 LINE SEPARATOR
U+2029 PARAGRAPH SEPARATOR
```

### Expected Statistics

| Statistic       | Value |
| --------------- | ----- |
| Byte Count      | ?     |
| Character Count | ?     |
| Word Count      | ?     |
| Line Count      | ?     |


