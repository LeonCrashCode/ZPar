cmake_minimum_required (VERSION 2.8.0)
project ("ZPar - A collections of sentence parsing tools")
set (EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/../dist)
set (SOURCE_DIR             ${PROJECT_SOURCE_DIR}/src)
include_directories (${SOURCE_DIR} ${SOURCE_DIR}/include)
include_directories (${SOURCE_DIR}/english)
set (CMAKE_CXX_FLAGS "-std=c++11 -g -w -W -O3 -DNDEBUG -DPERCEPTRON_FOR_DECODING -DTARGET_LANGUAGE=english")
include_directories (${SOURCE_DIR}/common/conparser)
include_directories (${SOURCE_DIR}/common/conparser/implementations/muhuan)
add_executable (english.conparser.parser
${SOURCE_DIR}/libs/reader.cpp
${SOURCE_DIR}/libs/writer.cpp
${SOURCE_DIR}/libs/options.cpp
${SOURCE_DIR}/libs/linguistics/lemma.cpp
${SOURCE_DIR}/libs/linguistics/conll.cpp
${SOURCE_DIR}/libs/learning/dbn.cpp
${SOURCE_DIR}/libs/linguistics/constituent.cpp
${SOURCE_DIR}/common/conparser/implementations/muhuan/conparser.cpp
${SOURCE_DIR}/common/conparser/implementations/muhuan/weight.cpp
${SOURCE_DIR}/common/conparser/main.cpp
)
set (CMAKE_CXX_FLAGS "-std=c++11 -g -w -W -O3 -DNDEBUG -DTARGET_LANGUAGE=english")
add_executable (english.conparser.train
${SOURCE_DIR}/libs/reader.cpp
${SOURCE_DIR}/libs/writer.cpp
${SOURCE_DIR}/libs/options.cpp
${SOURCE_DIR}/libs/linguistics/lemma.cpp
${SOURCE_DIR}/libs/linguistics/conll.cpp
${SOURCE_DIR}/libs/learning/dbn.cpp
${SOURCE_DIR}/libs/linguistics/constituent.cpp
${SOURCE_DIR}/common/conparser/implementations/muhuan/conparser.cpp
${SOURCE_DIR}/common/conparser/implementations/muhuan/weight.cpp
${SOURCE_DIR}/common/conparser/train.cpp
)
