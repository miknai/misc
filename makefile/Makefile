CPP = g++

# C++ compiler option (flags)
CXXFLAGS = -Wall -O2

# linker option
LDFLAGS =

# header file path
INCLUDE = -Iinclude/

# source file dir
SRC_DIR = ./src

# object file dir
OBJ_DIR = ./obj

# exe file name 
TARGET = main

# source names 
SRCS = $(notdir $(wildcard $(SRC_DIR)/*.cpp))

OBJS = $(SRCS:.cpp=.o)
DEPS = $(SRCS:.cpp=.d)

OBJECTS = $(patsubst %.o,$(OBJ_DIR)/%.o,$(OBJS))
DEPS = $(OBJECTS:.o=.d)

all: main

$(OBJ_DIR)/%.o : $(SRC_DIR)/%.cpp
	$(CPP) $(CXXFLAGS) $(INCLUDE) -c $< -o $@ -MD $(LDFLAGS)

$(TARGET) : $(OBJECTS)
	$(CPP) $(CXXFLAGS) $(OBJECTS) -o $(TARGET) $(LDFLAGS)

.PHONY: clean all
clean:
	rm -f $(OBJECTS) $(DEPS) $(TARGET)

-include $(DEPS)