cmake_minimum_required(VERSION 2.8)

project(LAStools)

include_directories(LASlib/inc LASzip/src)

add_definitions(-Wno-deprecated -DNDEBUG -DUNORDERED)

add_library(las
  SHARED
  LASlib/src/fopen_compressed.cpp
  LASlib/src/lasfilter.cpp
  LASlib/src/lasreader.cpp
  LASlib/src/lasreader_asc.cpp
  LASlib/src/lasreader_bil.cpp
  LASlib/src/lasreader_bin.cpp
  LASlib/src/lasreader_dtm.cpp
  LASlib/src/lasreader_las.cpp
  LASlib/src/lasreader_qfit.cpp
  LASlib/src/lasreader_shp.cpp
  LASlib/src/lasreader_txt.cpp
  LASlib/src/lasreaderbuffered.cpp
  LASlib/src/lasreadermerged.cpp
  LASlib/src/lasreaderpipeon.cpp
  LASlib/src/lastransform.cpp
  LASlib/src/lasutility.cpp
  LASlib/src/laswaveform13reader.cpp
  LASlib/src/laswaveform13writer.cpp
  LASlib/src/laswriter.cpp
  LASlib/src/laswriter_las.cpp
  LASlib/src/laswriter_bin.cpp
  LASlib/src/laswriter_qfit.cpp
  LASlib/src/laswriter_txt.cpp
  LASlib/src/laswriter_wrl.cpp
  LASlib/src/laswritercompatible.cpp
  LASzip/src/arithmeticdecoder.cpp
  LASzip/src/arithmeticencoder.cpp
  LASzip/src/arithmeticmodel.cpp
  LASzip/src/integercompressor.cpp
  LASzip/src/lasindex.cpp
  LASzip/src/lasinterval.cpp
  LASzip/src/lasquadtree.cpp
  LASzip/src/lasreaditemcompressed_v1.cpp
  LASzip/src/lasreaditemcompressed_v2.cpp
  LASzip/src/lasreadpoint.cpp
  LASzip/src/lasunzipper.cpp
  LASzip/src/laswriteitemcompressed_v1.cpp
  LASzip/src/laswriteitemcompressed_v2.cpp
  LASzip/src/laswritepoint.cpp
  LASzip/src/laszip.cpp
  LASzip/src/laszipper.cpp
)

install(TARGETS las DESTINATION lib EXPORT ${PROJECT_NAME}-targets)
install(EXPORT ${PROJECT_NAME}-targets DESTINATION lib/${PROJECT_NAME})

install(FILES
./LASlib/inc/lasdefinitions.hpp
./LASlib/inc/lasfilter.hpp
./LASlib/inc/lasreader_asc.hpp
./LASlib/inc/lasreader_bil.hpp
./LASlib/inc/lasreader_bin.hpp
./LASlib/inc/lasreaderbuffered.hpp
./LASlib/inc/lasreader_dtm.hpp
./LASlib/inc/lasreader.hpp
./LASlib/inc/lasreader_las.hpp
./LASlib/inc/lasreadermerged.hpp
./LASlib/inc/lasreaderpipeon.hpp
./LASlib/inc/lasreader_qfit.hpp
./LASlib/inc/lasreader_shp.hpp
./LASlib/inc/lasreader_txt.hpp
./LASlib/inc/lastransform.hpp
./LASlib/inc/lasutility.hpp
./LASlib/inc/laswaveform13reader.hpp
./LASlib/inc/laswaveform13writer.hpp
./LASlib/inc/laswriter_bin.hpp
./LASlib/inc/laswritercompatible.hpp
./LASlib/inc/laswriter.hpp
./LASlib/inc/laswriter_las.hpp
./LASlib/inc/laswriter_qfit.hpp
./LASlib/inc/laswriter_txt.hpp
./LASlib/inc/laswriter_wrl.hpp

./LASzip/src/arithmeticdecoder.hpp
./LASzip/src/arithmeticencoder.hpp
./LASzip/src/arithmeticmodel.hpp
./LASzip/src/bytestreamin_array.hpp
./LASzip/src/bytestreamin_file.hpp
./LASzip/src/bytestreamin.hpp
./LASzip/src/bytestreamin_istream.hpp
./LASzip/src/bytestreaminout_file.hpp
./LASzip/src/bytestreaminout.hpp
./LASzip/src/bytestreamout_array.hpp
./LASzip/src/bytestreamout_file.hpp
./LASzip/src/bytestreamout.hpp
./LASzip/src/bytestreamout_nil.hpp
./LASzip/src/bytestreamout_ostream.hpp
./LASzip/src/integercompressor.hpp
./LASzip/src/lasattributer.hpp
./LASzip/src/lasindex.hpp
./LASzip/src/lasinterval.hpp
./LASzip/src/laspoint.hpp
./LASzip/src/lasquadtree.hpp
./LASzip/src/lasquantizer.hpp
./LASzip/src/lasreaditemcompressed_v1.hpp
./LASzip/src/lasreaditemcompressed_v2.hpp
./LASzip/src/lasreaditem.hpp
./LASzip/src/lasreaditemraw.hpp
./LASzip/src/lasreadpoint.hpp
./LASzip/src/lasunzipper.hpp
./LASzip/src/laswriteitemcompressed_v1.hpp
./LASzip/src/laswriteitemcompressed_v2.hpp
./LASzip/src/laswriteitem.hpp
./LASzip/src/laswriteitemraw.hpp
./LASzip/src/laswritepoint.hpp
./LASzip/src/laszip_common_v1.hpp
./LASzip/src/laszip_common_v2.hpp
./LASzip/src/laszip.hpp
./LASzip/src/laszipper.hpp
./LASzip/src/mydefs.hpp
DESTINATION include/LAStools
)
