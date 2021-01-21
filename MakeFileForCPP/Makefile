#make file for cpp.. look at the make file of C for comments if you don't understand what these are
PROG := Bin/test
DEFINE = 
INCPATH = -ISource
CPPFLAGS += -Wall $(INCPATH) $(DEFINE)
CPPFLAGS += -O3
CPPFLAGS += -g
LFLAGS +=

CPP_SRCS = $(wildcard *.cpp) $(wildcard */*.cpp)
CPP_HDRS = $(wildcard *.hpp) $(wildcard */*.hpp)
CPP_DEPS = $(CPP_SRCS:.cpp=.d)
CPP_OBJS = $(CPP_SRCS:.cpp=.o)

OBJS :=  $(CPP_OBJS)

all: $(PROG)

$(PROG): $(OBJS)
	 $(CXX) $(LFLAGS) $^ -o $@

%.o: %.cpp
	$(CXX) $(CPPFLAGS) -MMD -c $< -o $@

clean:
	rm -f $(CPP_DEPS)
	rm -f $(OBJS)
	rm -f $(PROG)
