# This is a comment
#This make file expects the following 
#The source files should be in a folder/directory by the name 'Source'
#There should be a folder/directory named 'Bin' (The program will be generated there)


#USAGE
#make all
#make clean

#Name and Destination of the compiled program
PROG := Bin/test


DEFINE = 
#add the folder that you want to consider for compilation with a '-I' prefixing the folder name
INCPATH = -ISource

#flags for compilation
CFLAGS += -Wall $(INCPATH) $(DEFINE)

#add -O3 if you want optimization
CFLAGS += -O3

#add -g if you want debuggable binary
CFLAGS += -g

#linking flags..like havign math libraries
LFLAGS +=

C_SRCS = $(wildcard *.c) $(wildcard */*.c)
C_HDRS = $(wildcard *.h) $(wildcard */*.h)
C_DEPS = $(C_SRCS:.c=.d)
C_OBJS = $(C_SRCS:.c=.o)

OBJS :=  $(C_OBJS)

#creates the program/binary in the specified folder
all: $(PROG)

$(PROG): $(OBJS)
	 $(CC) $(LFLAGS) $^ -o $@

%.o: %.c
	$(CC) $(CFLAGS) -MMD -c $< -o $@

#remove past compiled programs and other object files
clean:
	rm -f $(C_DEPS)
	rm -f $(OBJS)
	rm -f $(PROG)
