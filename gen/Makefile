TARGETS=Makefile.include unicode.cpp unicode.h uninorms.cpp uninorms.h unistrip.cpp unistrip.h utf8.cpp utf8.h utf16.cpp utf16.h version.cpp version.h
UNILIB=3.1.2-devel
UNICODE=`date +%Y-%m-%d`

all:
	mkdir -p data
	curl https://unicode.org/Public/UCD/latest/ucd/UnicodeData.txt | xz -c9v > data/UnicodeData.txt.xz
	curl https://unicode.org/Public/UCD/latest/ucd/CompositionExclusions.txt | xz -c9v > data/CompositionExclusions.txt.xz
	curl https://unicode.org/Public/UCD/latest/ucd/NormalizationTest.txt | xz -c9v > data/NormalizationTest.txt.xz
	./generate.pl $(UNILIB) "$(UNICODE)" data/UnicodeData.txt.xz data/CompositionExclusions.txt.xz $(foreach t,$(TARGETS),template/$(t) ../unilib/$(t))
