LD_LIBRARY_PATH=/usr/local/lib/

CURDIR=$(shell pwd)
#SRC=Main.cpp ./Calculator.cpp ./CalculatorTest.cpp
SRC=$(CURDIR)/src/money.cpp    \
    $(CURDIR)/test/money_test.cpp    \
    $(CURDIR)/test/money_test_main.cpp    \
    
CXX=g++
CC=gcc
CXXFLAGS=-I src/ -I test/ -I /usr/local/include/cppunit/
libflag = -L /usr/local/lib
#LDFLAGS=-lcppunit -ldl

LDFLAGS=-lcppunit -lrt -lcurses -ldl
TESTFLAG = -ftest-coverage -fprofile-arcs
All:main

main: $(SRC)
	$(CXX) -o $@ $(SRC) $(CXXFLAGS) $(LDFLAGS) ${libflag} -pg ${TESTFLAG}
clean:
	rm -f *.o *.gcno *.gcda *.out main
