CURDIR=$(shell pwd)
LD_LIBRARY_PATH=/usr/local/lib/

#SRC=$(CURDIR)/src/add.cc    \
    $(CURDIR)/test/testAdd.cc    \
    
CXX=g++
CC=gcc
CXXFLAGS=-I src/ -I test/ -I /usr/local/include/gtest/
libflag = -L /usr/local/lib
LDFLAGS=-lgtest -lgtest_main -lpthread -std=c++11
TESTFLAG = -ftest-coverage -fprofile-arcs

FILES = $(foreach d, $(CURDIR), $(wildcard $(d)/src/*.cpp))
FILES += $(foreach d, $(CURDIR), $(wildcard $(d)/test/*.cpp))



all: run_test
run_test:
	$(CXX) -o $@ $(FILES) $(CXXFLAGS) $(LDFLAGS) -pg ${TESTFLAG}

clean:
	rm -f *.o src/*.o test/*.o *.gcno *.gcda *.out *.gcov *.info run_test
	rm -rf result
