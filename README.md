# Aurum Script

This is a simplistic text encoding format that focuses on ligatures; joining multiple base symbols into more complex shapes.

There's a few base symbols that combine to create most of the modern symbols anyone would need and want for communication. Each base is exactly 16 bits, giving 65536 possible bases.

- Base 0 is reserved for no data, serving a functionaly near-identical purpose as `\0` in C.
- Base 1 is the deliminer. An interchangable spacer between groups of symbols for any script built on Aurum Script. It also serves as a hard deliminer between any base symbols to prevent further joining.
- Base 2 is the soft deliminer. It does not space groups of symbols but prevents further joining.
- From base 3 and on they represent real symbols.

Symbols refer to any visual stroke or syntax rule.

Joining symbols is the process of taking a list of symbols that do not include any B0-2 bases, and going from start to finish, joining together the largest groups of symbols based on join rules.

Join rules are the basis of complex symbols. They define how 2 or more symbols join to become a more complex shape. These join rules are there to represent more complex shapes that cannot fit in the bases and still is required to be a single symbol. This is useful for font ligatures, support for symbols outside the immediate base group and conversion between text encoding formats. Fonts or rendering systems must define these join rules themselves.

## Bases

### `0+` Syntax rules

| Base number | Name | Description / Sample |
| --- | --- | --- |
| 0 | Null | |
| 1 | Hard deliminer | |
| 2 | Soft deliminer | |
| 3 | Maintain layout direction LRTB | Read: →,↓ |
| 4 | Maintain layout direction RLTB | Read: ←,↓ |
| 5 | Maintain layout direction LRBT | Read: →,↑ |
| 6 | Maintain layout direction RLBT | Read: ←,↑ |
| 7 | Maintain layout direction TBLR | Read: ↓,→ |
| 8 | Maintain layout direction TBRL | Read: ↓,← |
| 9 | Maintain layout direction BTLR | Read: ↑,→ |
| 10 | Maintain Layout direction BTRL | Read: ↑,← |
| 11 | Maintain font weight 0 | <t style="font-weight: 100;">Sample text</t> |
| 12 | Maintain font weight 0.25 | <t style="font-weight: 200;">Sample text</t> |
| 13 | Maintain font weight 0.5 | <t style="font-weight: 300;">Sample text</t> |
| 14 | Maintain font weight 0.75 | <t style="font-weight: 400;">Sample text</t> |
| 15 | Maintain font weight 1 | <t style="font-weight: 500;">Sample text</t> |
| 16 | Maintain font weight 1.25 | <t style="font-weight: 600;">Sample text</t> |
| 17 | Maintain font weight 1.5 | <t style="font-weight: 700;">Sample text</t> |
| 18 | Maintain font weight 1.75 | <t style="font-weight: 800;">Sample text</t> |
| 19 | Maintain font weight 2 | <t style="font-weight: 900;">Sample text</t> |
| 20 | Maintain font italic | <i>Sample text</i> |
| 21 | Maintain font underline | <u>Sample text</u> |
| 22 | Maintain font strikethrough | <s>Sample text</s> |
| 23 | Maintain font just (non-sub & non-sup) | Sample text |
| 24 | Maintain font superscript | <sup>Sample text</sup> |
| 25 | Maintain font subscript | <sub>Sample text</sub> |
| 26 | Maintain font reset | Sample text |

### `256+` Universal/common symbols

| Base number | Name | Unicode representation |
| --- | --- | --- |
| 256 | Horizonal line | ― |
| 257 | Vertical line | \| |
| 258 | Diagonal line | \\ |
| 259 | Hollow square | □ |
| 260 | Diagonal line | / |
| 261 | Filled square | ■ |
| 262 | Hollow circle | ○ |
| 263 | Filled circle | ● |
| 264 | Hollow triangle (up) | △ |
| 265 | Hollow triangle (down) | ▽ |
| 266 | Hollow triangle (left) | ◁ |
| 267 | Hollow triangle (right) | ▷ |
| 268 | Filled triangle (up) | ▲ |
| 269 | Filled triangle (down) | ▼ |
| 270 | Filled triangle (left) | ◂ |
| 271 | Filled triangle (right) | ▸ |

### `512+` Latin (basic + extended for Western/Eastern European, Vietnamese, ASCII subset, etc.)

| Base number | Name | Unicode representation |
| --- | --- | --- |
| 512 | Latin letter "A" | A |
| 513 | Latin letter "B" | B |
| 514 | Latin letter "C" | C |
| 515 | Latin letter "D" | D |
| 516 | Latin letter "E" | E |
| 517 | Latin letter "F" | F |
| 518 | Latin letter "G" | G |
| 519 | Latin letter "H" | H |
| 520 | Latin letter "I" | I |
| 521 | Latin letter "J" | J |
| 522 | Latin letter "K" | K |
| 523 | Latin letter "L" | L |
| 524 | Latin letter "M" | M |
| 525 | Latin letter "N" | N |
| 526 | Latin letter "O" | O |
| 527 | Latin letter "P" | P |
| 528 | Latin letter "Q" | Q |
| 529 | Latin letter "R" | R |
| 530 | Latin letter "S" | S |
| 531 | Latin letter "T" | T |
| 532 | Latin letter "U" | U |
| 533 | Latin letter "V" | V |
| 534 | Latin letter "W" | W |
| 535 | Latin letter "X" | X |
| 536 | Latin letter "Y" | Y |
| 537 | Latin letter "Z" | Z |
| 538 | Latin letter "a" | a |
| 539 | Latin letter "b" | b |
| 540 | Latin letter "c" | c |
| 541 | Latin letter "d" | d |
| 542 | Latin letter "e" | e |
| 543 | Latin letter "f" | f |
| 544 | Latin letter "g" | g |
| 545 | Latin letter "h" | h |
| 546 | Latin letter "i" | i |
| 547 | Latin letter "j" | j |
| 548 | Latin letter "k" | k |
| 549 | Latin letter "l" | l |
| 550 | Latin letter "m" | m |
| 551 | Latin letter "n" | n |
| 552 | Latin letter "o" | o |
| 553 | Latin letter "p" | p |
| 554 | Latin letter "q" | q |
| 555 | Latin letter "r" | r |
| 556 | Latin letter "s" | s |
| 557 | Latin letter "t" | t |
| 558 | Latin letter "u" | u |
| 559 | Latin letter "v" | v |
| 560 | Latin letter "w" | w |
| 561 | Latin letter "x" | x |
| 562 | Latin letter "y" | y |
| 563 | Latin letter "z" | z |
| 585 | Latin letter "ı" | ı |
| 564 | Latin diactric "acute" | ´ |
| 565 | Latin diactric "grave" | ` |
| 566 | Latin diactric "circumflex" | ˆ |
| 567 | Latin diactric "tilde" | ˜ |
| 568 | Latin diactric "umlaut/diaeresis" | ¨ |
| 569 | Latin diactric "double acute" | ˝ |
| 570 | Latin diactric "ring" | ˚ |
| 571 | Latin diactric "cedilla" | ¸ |
| 572 | Latin diactric "caron/háček" | ˇ |
| 573 | Latin diactric "breve" | ˘ |
| 574 | Latin diactric "macron" | ¯ |
| 576 | Latin diactric "dot above" | ˙ |
| 577 | Latin diactric "dot below" | ̣ |
| 578 | Latin diactric "ogonek" | ˛ |
| 579 | Latin diactric "stroke" | / |
| 580 | Latin diactric "glottal stop modifier" | ˀ |
| 581 | Latin diactric "reversed glottal stop" | ˁ |
| 582 | Latin diactric "reversed comma" | ʽ |
| 583 | Latin diactric "hamza-like" | ʾ |
| 584 | Latin diactric "ayin-like" | ʿ |
| 586 | Latin punctuation "period" | . |
| 587 | Latin punctuation "comma" | , |
| 588 | Latin punctuation "question mark" | ? |
| 589 | Latin punctuation "exclamation mark" | ! |
| 590 | Latin punctuation "colon" | : |
| 591 | Latin punctuation "semicolon" | ; |
| 592 | Latin punctuation "hyphen" | \- |
| 593 | Latin punctuation "em dash | — |
| 594 | Latin punctuation "en dash | – |
| 595 | Latin punctuation "ellipsis | … |
| 596 | Latin punctuation "opening parenthesis" | \( |
| 597 | Latin punctuation "closing parenthesis" | \) |
| 598 | Latin punctuation "opening bracket" | \[ |
| 599 | Latin punctuation "closing bracket" | \] |
| 600 | Latin punctuation "opening brace" | \{ |
| 601 | Latin punctuation "closing brace" | \} |
| 602 | Latin punctuation "opening chevron" | < |
| 603 | Latin punctuation "closing chevron" | > |

### `768+` Cyrillic (basic + extended for Slavic and non-Slavic languages)

| Base number | Name | Unicode representation |
| --- | --- | --- |
| 768 | Cyrillic letter "А" | А |
| 769 | Cyrillic letter "Б" | Б |
| 770 | Cyrillic letter "В" | В |
| 771 | Cyrillic letter "Г" | Г |
| 772 | Cyrillic letter "Д" | Д |
| 773 | Cyrillic letter "Є" | Є |
| 774 | Cyrillic letter "Ж" | Ж |
| 775 | Cyrillic letter "Ꙃ" | Ꙃ |
| 776 | Cyrillic letter "Ꙁ" | Ꙁ |
| 777 | Cyrillic letter "И" | И |
| 778 | Cyrillic letter "Ї" | Ї |
| 779 | Cyrillic letter "Ꙉ" | Ꙉ |
| 780 | Cyrillic letter "К" | К |
| 781 | Cyrillic letter "Л" | Л |
| 782 | Cyrillic letter "М" | М |
| 783 | Cyrillic letter "Н" | Н |
| 784 | Cyrillic letter "О" | О |
| 785 | Cyrillic letter "П" | П |
| 786 | Cyrillic letter "Ҁ" | Ҁ |
| 787 | Cyrillic letter "Р" | Р |
| 788 | Cyrillic letter "С" | С |
| 789 | Cyrillic letter "Т" | Т |
| 790 | Cyrillic letter "У" | У |
| 791 | Cyrillic letter "Ф" | Ф |
| 792 | Cyrillic letter "Х" | Х |
| 793 | Cyrillic letter "Ѡ" | Ѡ |
| 794 | Cyrillic letter "Ѿ" | Ѿ |
| 795 | Cyrillic letter "Ц" | Ц |
| 796 | Cyrillic letter "Ч" | Ч |
| 797 | Cyrillic letter "Ш" | Ш |
| 798 | Cyrillic letter "Щ" | Щ |
| 799 | Cyrillic letter "Ъ" | Ъ |
| 800 | Cyrillic letter "Ь" | Ь |
| 801 | Cyrillic letter "Ѣ" | Ѣ |
| 802 | Cyrillic letter "Ꙗ" | Ꙗ |
| 803 | Cyrillic letter "Ѥ" | Ѥ |
| 804 | Cyrillic letter "Ю" | Ю |
| 805 | Cyrillic letter "Ѫ" | Ѫ |
| 806 | Cyrillic letter "Ѭ" | Ѭ |
| 807 | Cyrillic letter "Ѧ" | Ѧ |
| 808 | Cyrillic letter "Ѩ" | Ѩ |
| 809 | Cyrillic letter "Ѯ" | Ѯ |
| 810 | Cyrillic letter "Ѱ" | Ѱ |
| 811 | Cyrillic letter "Ѳ" | Ѳ |
| 812 | Cyrillic letter "Ѵ" | Ѵ |
| 813 | Cyrillic letter "Ґ" | Ґ |
| 814 | Cyrillic letter "а" | а |
| 815 | Cyrillic letter "б" | б |
| 816 | Cyrillic letter "в" | в |
| 817 | Cyrillic letter "г" | г |
| 818 | Cyrillic letter "д" | д |
| 819 | Cyrillic letter "є" | є |
| 820 | Cyrillic letter "ж" | ж |
| 821 | Cyrillic letter "ꙃ" | ꙃ |
| 822 | Cyrillic letter "ꙁ" | ꙁ |
| 823 | Cyrillic letter "и" | и |
| 824 | Cyrillic letter "ї" | ї |
| 825 | Cyrillic letter "ꙉ" | ꙉ |
| 826 | Cyrillic letter "к" | к |
| 827 | Cyrillic letter "л" | л |
| 828 | Cyrillic letter "м" | м |
| 829 | Cyrillic letter "н" | н |
| 830 | Cyrillic letter "о" | о |
| 831 | Cyrillic letter "п" | п |
| 832 | Cyrillic letter "ҁ" | ҁ |
| 833 | Cyrillic letter "р" | р |
| 834 | Cyrillic letter "с" | с |
| 835 | Cyrillic letter "т" | т |
| 836 | Cyrillic letter "у" | у |
| 837 | Cyrillic letter "ф" | ф |
| 838 | Cyrillic letter "х" | х |
| 839 | Cyrillic letter "ѡ" | ѡ |
| 840 | Cyrillic letter "ѿ" | ѿ |
| 841 | Cyrillic letter "ц" | ц |
| 842 | Cyrillic letter "ч" | ч |
| 843 | Cyrillic letter "ш" | ш |
| 844 | Cyrillic letter "щ" | щ |
| 845 | Cyrillic letter "ъ" | ъ |
| 846 | Cyrillic letter "ь" | ь |
| 847 | Cyrillic letter "ѣ" | ѣ |
| 848 | Cyrillic letter "ꙗ" | ꙗ |
| 849 | Cyrillic letter "ѥ" | ѥ |
| 850 | Cyrillic letter "ю" | ю |
| 851 | Cyrillic letter "ѫ" | ѫ |
| 852 | Cyrillic letter "ѭ" | ѭ |
| 853 | Cyrillic letter "ѧ" | ѧ |
| 854 | Cyrillic letter "ѩ" | ѩ |
| 855 | Cyrillic letter "ѯ" | ѯ |
| 856 | Cyrillic letter "ѱ" | ѱ |
| 857 | Cyrillic letter "ѳ" | ѳ |
| 858 | Cyrillic letter "ѵ" | ѵ |
| 859 | Cyrillic letter "ґ" | ґ |
| 860 | Cyrillic letter "ә" | ә |
| 861 | Cyrillic letter "ғ" | ғ |
| 862 | Cyrillic letter "қ" | қ |
| 863 | Cyrillic letter "ң" | ң |
| 864 | Cyrillic letter "ө" | ө |
| 865 | Cyrillic letter "ұ" | ұ |
| 866 | Cyrillic letter "ү" | ү |
| 867 | Cyrillic letter "ҳ" | ҳ |
| 868 | Cyrillic letter "һ" | һ |
| 867 | Cyrillic diactric "titlo" | ҃ |
| 867 | Cyrillic diactric "pokrytie" | ҇ |
| 868 | Cyrillic numeral "thousand" | ҂ |

### `1024+` Greek (including Coptic)

| Base number | Name | Unicode representation |
| --- | --- | --- |
| 1024 | Greek letter "Α" | Α |
| 1025 | Greek letter "Β" | Β |
| 1026 | Greek letter "Γ" | Γ |
| 1027 | Greek letter "Δ" | Δ |
| 1028 | Greek letter "Ε" | Ε |
| 1029 | Greek letter "Ζ" | Ζ |
| 1030 | Greek letter "Η" | Η |
| 1031 | Greek letter "Θ" | Θ |
| 1032 | Greek letter "Ι" | Ι |
| 1033 | Greek letter "Κ" | Κ |
| 1034 | Greek letter "Λ" | Λ |
| 1035 | Greek letter "Μ" | Μ |
| 1036 | Greek letter "Ν" | Ν |
| 1037 | Greek letter "Ξ" | Ξ |
| 1038 | Greek letter "Ο" | Ο |
| 1039 | Greek letter "Π" | Π |
| 1040 | Greek letter "Ρ" | Ρ |
| 1041 | Greek letter "Σ" | Σ |
| 1042 | Greek letter "Τ" | Τ |
| 1043 | Greek letter "Υ" | Υ |
| 1044 | Greek letter "Φ" | Φ |
| 1045 | Greek letter "Χ" | Χ |
| 1046 | Greek letter "Ψ" | Ψ |
| 1047 | Greek letter "Ω" | Ω |
| 1048 | Greek letter "α" | α |
| 1049 | Greek letter "β" | β |
| 1050 | Greek letter "γ" | γ |
| 1051 | Greek letter "δ" | δ |
| 1052 | Greek letter "ε" | ε |
| 1053 | Greek letter "ζ" | ζ |
| 1054 | Greek letter "η" | η |
| 1055 | Greek letter "θ" | θ |
| 1056 | Greek letter "ι" | ι |
| 1057 | Greek letter "κ" | κ |
| 1058 | Greek letter "λ" | λ |
| 1059 | Greek letter "μ" | μ |
| 1060 | Greek letter "ν" | ν |
| 1061 | Greek letter "ξ" | ξ |
| 1062 | Greek letter "ο" | ο |
| 1063 | Greek letter "π" | π |
| 1064 | Greek letter "ρ" | ρ |
| 1065 | Greek letter "σ" | σ |
| 1066 | Greek letter "τ" | τ |
| 1067 | Greek letter "υ" | υ |
| 1068 | Greek letter "φ" | φ |
| 1069 | Greek letter "χ" | χ |
| 1070 | Greek letter "ψ" | ψ |
| 1071 | Greek letter "ω" | ω |
| 1072 | Greek letter "ς" | ς |
| 1073 | Coptic Capital "Šai" | Ϣ |
| 1074 | Coptic Small "šai" | ϣ |
| 1075 | Coptic Capital "Hori" | Ϥ |
| 1076 | Coptic Small "hori" | ϥ |
| 1077 | Coptic Capital "Gangia" | Ϧ |
| 1078 | Coptic Small "gangia" | ϧ |
| 1079 | Coptic Capital "Bau" | Ϩ |
| 1080 | Coptic Small "bau" | ϩ |
| 1081 | Coptic Capital "Čima" | Ϫ |
| 1082 | Coptic Small "čima" | ϫ |
| 1083 | Coptic Capital "Ti" | Ϭ |
| 1084 | Coptic Small "ti" | ϭ |
| 1085 | Coptic Capital "Kji" | Ϯ |
| 1086 | Coptic Small "kji" | ϯ |
| 1087 | Greek Capital "Digamma" | Ϝ |
| 1088 | Greek Small "digamma" | ϝ |
| 1089 | Greek Capital "Stigma" | Ϛ |
| 1090 | Greek Small "stigma" | ϛ |
| 1091 | Greek Capital "Koppa" | Ϙ |
| 1092 | Greek Small "koppa" | ϙ |
| 1093 | Greek Capital "Sampi" | Ϡ |
| 1094 | Greek Small "sampi" | ϡ |
| 1095 | Coptic Capital "Old Coptic Esh" | Ⲁ |
| 1096 | Coptic Small "Old Coptic Esh" | ⲁ |
| 1097 | Coptic Capital "Old Coptic Hori" | Ⲃ |
| 1098 | Coptic Small "Old Coptic Hori" | ⲃ |
| 1099 | Coptic Capital "Old Coptic Ha" | Ⲅ |
| 1100 | Coptic Small "Old Coptic Ha" | ⲅ |
| 1101 | Coptic Capital "Old Coptic Shei" | Ⲋ |
| 1102 | Coptic Small "Old Coptic Shei" | ⲋ |
| 1103 | Coptic Capital "Old Coptic Fei" | Ⲍ |
| 1104 | Coptic Small "Old Coptic Fei" | ⲍ |
| 1105 | Coptic Capital "Old Coptic Khat" | Ⲑ |
| 1106 | Coptic Small "Old Coptic Khat" | ⲑ |
| 1107 | Greek Ano Teleia (High Dot) | · |
| 1108 | Greek Hyphen | ͺ |
| 1109 | Greek Koronis | ̓ |
| 1110 | Greek Dialytika Tonos | ̈́ |
| 1111 | Greek Lower Numeral Sign | ͵ |
| 1112 | Greek Numeral Sign | ʹ |
| 1113 | Coptic Old Nubian Full Stop | ⳾ |
| 1114 | Coptic Old Nubian Comma | ⳿ |
| 1115 | Coptic Cross (Stauros) | ⳨ |
| 1116 | Coptic Capital "Cyrillic" Es | Ⲥ |
| 1117 | Coptic Small "Cyrillic" es | ⲥ |
| 1118 | Coptic Combining Long Stroke | ⳰ |
| 1119 | Coptic Combining Vowel Mark | ⳱ |

### `1280+` Arabic (basic letters, diacritics, and presentation forms)

### `1536+` Hebrew (including cantillation marks if needed)

### `1792+` Devanagari (basic consonants, vowel signs, and modifiers)

### `2048+` Chinese

### `2304+` Japanese

### `2560+` Korean

### `2816+` Thai, Lao, Khmer, Myanmar (Southeast Asian abugidas)

### `3072+` Ethiopic
