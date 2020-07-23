g++ -std=c++11 -o main main_test.cpp -lgtest -I googletest/googletest/include/

g++ -std=c++11 -o test -fprofile-arcs -ftest-coverage -lgtest main_test.cpp -I googletest/googletest/include/