Slabo
=========

#### v1.01, 28 January 2014

Slabo is a collection of size-specific fonts for use in online advertising and other web uses. The Slabo fonts and sources are released under the SIL Open Font License 1.1; if needful, licensing under Apache 2.0 is negotiable from Tiro Typeworks Ltd., contact <license@tiro.ca>.

The Slabo repository consists of TrueType `.ttf` font files, FontLab Studio `.vfb` sources, UFO format derived sources, and MS VOLT OpenType Layout `.vtp` sources, along with some glyph set documentation and FontLab support files.

The initial development of the Slabo fonts was done in FontLab Studio 5, with OpenType Layout table work done in MS VOLT, and the sources provided reflect this. The `.vfb` files contain the original TrueType outlines and semi-automated visual hints in FontLab's internal representation, as well as class-based kerning data. Note however, that because OTL tables were developed in MS VOLT, the shipped fonts do not contain kerning generated from the FontLab sources, but instead implementation of the same kerning data in VOLT. The VOLT sources are `.vtp` format; this is a plain text representation of the VOLT project that can be imported into VOLT. The `.fea` files describe the same OTL behaviour in [AFDKO's feature file syntax](http://www.adobe.com/devnet/opentype/afdko/topic_feature_file_syntax.html).

After compilation from VOLT, the `.ttf` fonts have undergone light post-processing to update the OS/2 table usMaxContext field. I use DTL OTMaster for this, but someone wanting to perform similar table edits with an open source tool could use e.g. TTX.

The UFO files are a derived source, exported from FontLab Studio 5 using Tal Leming's UFO Central macro. They are provided as is.

The FontLab Sources folder contains not only the `.vfb` files for the size-specific fonts, but also the generic model design from which the size-specific variants are derived. This is referred to as 'Slabo Xpx'. Note that this design was never intended to ship as a font, but only as a source for derived designs; as such, it contains numerous outline overlaps and other features to assist editing but what would be errors in a shipped font.

The Support Files folder contains a `.ods` format spreadsheet that documents the initial Slabo glyph set. This set covers a superset of the Windows 1252 (Latin 1), 1250 (Eastern Europe), 1254 (Turkish), and 1257 (Baltic) codepages, as well as most of the Mac Roman charset (initial release is missing some generic symbol characters). The other files in that folder are `.enc`, `.nam` and `.ren` files for glyph set management in FontLab Studio.

— John Hudson
