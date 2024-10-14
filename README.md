# Nutso

#### NOTE: test fonts are available in the [third_party](third_party/) folder.

# Licensing

[![Creative Commons Zero](http://i.creativecommons.org/p/zero/1.0/88x31.png)](http://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, John Hudson has waived all copyright and related or neighboring rights to Nutso.
Nutso is available under the terms of "Creative Commons Zero" and full details are in [LICENSE.txt](LICENSE.txt)

The files in the [third_party](third_party/) directory are a combination of Nutso and a subset of the Noto Serif fonts, provided as a _proof of concept_ working example.
The version of Noto Serif used is licensed under the Apache License 2.0, so those example fonts are also licensed the same way. 
They are kept in a separate directory to clarify this different licensing status, along with a copy of the Apache license itself.

# Release Notes

#### Nutso2 v1.03, 21 February 2014

Nutso2 is an alternative stacked fraction implementation that enables fractions with longer numerators than denominators. In this implementation, the fraction bars exist as independent, spacing glyphs of variant width, and both numerators and denominators are handled as mark glyphs. The numerators are contextually positioned relative to the invisible 'fracinit' glyph that marks the beginning of the fraction, as in Nutso, while the denominators are positioned relative to the bar. The length of bar used is dependent on the longer of the numerator or denominator string.

NB. Tracking functions will still mess with the fraction alignment, albeit in a different way from how they mess with Nutso, and should not be applied to text formatted as fractions.

Thanks to Kent Lew for putting the idea for the Nutso2 implementation in my head.

#### Nutso update, 21 February 2014

Nutso [AFDKO .fea code](http://www.adobe.com/devnet/opentype/afdko/topic_feature_file_syntax.html) and a CFF OT font contributed by Miguel Sousa added. The .fea code provides a different tool path and can be utilised directly in AFDKO or in third party tools that make use of that library.

#### Nutso v1.02, 19 February 2014

Nutso is font, based on Google's Noto outlines, that includes a small set of characters and glyph variants to produce on-the-fly arbitrary 'nut' fractions, i.e. vertically stacked fractions. This display behaviour is implemented in OpenType Layout GSUB and GPOS tables, and can be applied to runs of characters in text of the format 'x/y' where y is any numeral or sequence of multiple numerals <11, and x is any numeral or sequence of numerals less than or equal to y (in other words, the numerator of the fraction cannot be longer than the denominator). It would be possible to extend the logic to accommodate longer denominator sequences, but 10 seemed like a reasonable limit; OpenType Layout context statements are simple lists, so a fixed limit is necessary.

The OTL lookups in Nutso apply the same layout to both the OTL `<frac>` and `<afrc>` features. In another font, `<frac>` could be reserved for diagonal fractions, and `<afrc>` used for nut fractions. Note that the current implementation also requires the `<mark>` and `<mkmk>` features to be supported and active. A different implementation requiring a larger number of glyphs could be made to work with just the `<frac>`/`<afrc>` features, but would still rely on both GSUB and GPOS lookups.

Some care needs to be taken when editing text employing nut fractions implemented as in Nutso: the fraction feature must only be applied to discreet runs of characters in the appropriate format, and tracking (letterspacing) functions must not be applied to the fractions.

The initial release consists of the Nutso `.ttf` compiled font file and the `.vtp` [Microsoft VOLT](http://www.microsoft.com/typography/volt.mspx) OTL source file. The latter is a plain text representation of the VOLT project, which can be imported and merged with the font file in the VOLT tool.

— John Hudson
