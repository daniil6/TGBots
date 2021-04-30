CXX      = g++
CXXFLAGS = -O2 -Wall -DNDEBUG 
LDFLAGS  = -static -s

OPENSSL  = ..\botlibs\openssl
TGBOT    = ..\botlibs\tgbot
BOOST    = ..\botlibs\boost

SOURCES  = main.cpp
FILE_OUT = bot.exe

OBJECTS = $(SOURCES:.cpp=.cpp.o)
TARGET = $(SOURCES:.cpp=.task)

LIST_INCLUDE = \
    -I$(OPENSSL)\include -I$(TGBOT)\include -I$(BOOST)

LIST_LIBS = \
    -L$(OPENSSL)\lib -L$(TGBOT)\lib

LIBRARIES = \
    -lTgBot -lssl -lcrypto -lws2_32 -lgdi32 -lcrypt32
	
all: $(TARGET) link
	
%.task:
	$(CXX) -c $(@:.task=).cpp $(CXXFLAGS) $(LIST_INCLUDE) -o $(@:.task=).cpp.o

link:
	$(CXX) $(OBJECTS) $(LDFLAGS) $(LIST_LIBS) $(LIBRARIES) -o $(FILE_OUT)