Nutso
=========

#### v1.02, 19 February 2014

Nutso is font, based on Google's Noto outlines, that includes a small set of characters and glyph variants to produce on-the-fly arbitrary 'nut' fractions, i.e. vertically stacked fractions. This display behaviour is implemented in OpenType Layout GSUB and GPOS tables, and can be applied to runs of characters in text of the format 'x/y' where y is any numeral or sequence of multiple numerals <11, and x is any numeral or sequence of numerals less than or equal to y (in other words, the numerator of the fraction cannot be longer than the denominator). It would be possible to extend the logic to accommodate longer denominator sequences, but 10 seemed like a reasonable limit; OpenType Layout context statements are simple lists, so a fixed limit is necessary.

The OTL lookups in Nutso apply the same layout to both the OTL <frac> and <afrc> features. In another font, <frac> could be reserved for diagonal fractions, and <afrc> used for nut fractions. Note that the current implementation also requires the <mark> and <mkmk> features to be supported and active. A different implementation requiring a larger number of glyphs could be made to work with just the <frac>/afrc> features, but would still rely on both GSUB and GPOS lookups.

Some care needs to be taken when editing text employing nut fractions implemented as in Nutso: the fraction feature must only be applied to discreet runs of characters in the appropriate format, and tracking (letterspacing) functions must not be applied to the fractions.

The initial release consists of the Nutso `.ttf` compiled font file and the `.vtp` Microsoft VOLT OTL source file. The latter is a plain text representation of the VOLT project, which can be imported and merged with the font file in the VOLT tool.

— John Hudson