# 说明

离散型切片和mbtiles 之间的转换工具



# 使用

## Quick Start

~~~shell
# 注意：转换前，目标文件夹/文件必须不存在
# 将 world.mbtiles 转为 tiles 文件夹形式（文件夹内为离散性切片文件）
mb-util.exe world.mbtiles tiles

# 将 tiles 文件夹形式转为 world.mbtiles
mb-util.exe tiles world.mbtiles
~~~

## Help

~~~shell
mb-util.exe --help
~~~

~~~
Usage: mb-util.exe [options] input output

    Examples:

    Export an mbtiles file to a directory of files:
    $ mb-util world.mbtiles dumps # when the 2nd argument is "dumps", then dumps the metatdata.json

    Export an mbtiles file to a directory of files:
    $ mb-util world.mbtiles tiles # tiles must not already exist

    Import a directory of tiles into an mbtiles file:
    $ mb-util tiles world.mbtiles # mbtiles file must not already exist

Options:
  -h, --help            show this help message and exit
  --scheme=SCHEME       Tiling scheme of the tiles. Default is "xyz" (z/x/y),
                        other options are "tms" which is also z/x/y but uses a
                        flipped y coordinate, and "wms" which replicates the
                        MapServer WMS TileCache directory structure
                        "z/000/000/x/000/000/y.png"
  --image_format=FORMAT
                        The format of the image tiles, either png, jpg, webp
                        or pbf
  --grid_callback=CALLBACK
                        Option to control JSONP callback for UTFGrid tiles. If
                        grids are not used as JSONP, you can remove callbacks
                        specifying --grid_callback=""
  --do_compression      Do mbtiles compression
  --silent              Dictate whether the operations should run silently
~~~

