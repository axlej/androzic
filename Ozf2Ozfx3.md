# Introduction #

Ozf format is very well optimized for mobile solutions where memory is a great issue. There is no possibility to load full map image into memory in commonly used raster graphics formats. And these formats are not optimized or sometimes even not suitable for loading small parts of image. This is where ozf format comes in place. It stores map image in tiles and each tile can be quickly individually referenced to be read from file on demand. Each tile is also optimized to use up to four times less disk space than in common graphics format.

Rescaling is also CPU consuming function and is critical for performance on mobile devices. That's why ozf file contains prescaled images of the map. But scales are selected slightly different in old and modern versions on Img2ozf: older versions generated bigger scales (80%, 70%, 60%, etc) while modern versions generate only smaller scales (25%, 10%, 5%, etc). Most likely it is due to increased average performance of modern mobile devices and desire to make map image files smaller.

# Ozf2 or Ozfx3? #

Through ozf2 and ozfx3 files have some minor difference in header structure all map image data is stored absolutely identically with only one change: ozfx3 file is for some fatuous reason encoded. It means that extra CPU resources are used for decoding on each file access which is not wise on still relatively slow mobile devices. There are no any benefits of using ozfx3 format at all, so I will recommend continuing to use ozf2 format.

Lately OziExplorer author made another change in ozfx3 format cutting compatibility with its own applications: now file is encoded using RC4 algorithm instead of homemade XOR. Androzic does not support this format for the time being that's why older versions of Img2ozf and MapMerge should be used to convert maps.