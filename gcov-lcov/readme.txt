g++ -std=c++11 -o main main_test.cpp -lgtest -I googletest/googletest/include/

g++ -std=c++11 -o test -fprofile-arcs -ftest-coverage -lgtest main_test.cpp -I googletest/googletest/include/

g++ -std=c++11 -o test -fprofile-arcs -ftest-coverage -lgtest --coverage main_test.cpp -I googletest/googletest/include/

lcov --capture --directory . --output-file=coverage.info

genhtml coverage.info --output-directory=res