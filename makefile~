# Project_name
TARGET = $(BIN_DIR)/pesca

# Libraries
LIBS = -lpthread -lrt -lm

# Compiler
CC = gcc

# Compiler_Flags
CFLAGS = -iquote$(INC_DIR)

# Folders
BASE_DIR = pesca
SRC_DIR  = src
INC_DIR  = include
OBJ_DIR  = obj
TEST_DIR = testes
BIN_DIR  = bin

# Include_files

BARCO_H = $(INC_DIR)/barco.h
CAPITAO_H = $(INC_DIR)/capitao.h
CARDUME_H = $(INC_DIR)/cardume.h
FIFO_H = $(INC_DIR)/fifo.h
MUNDO_H = $(INC_DIR)/mundo.h
PARAMETROS_H = $(INC_DIR)/parametros.h
POSICAO_H = $(INC_DIR)/posicao.h
SEMAPHORE_H = $(INC_DIR)/semaphore.h
SHARED_H = $(INC_DIR)/shared.h
UTIL_H = $(INC_DIR)/util.h

# Source_files

BARCO_C = $(SRC_DIR)/barco.c
CAPITAO_C = $(SRC_DIR)/capitao.c
CARDUME_C = $(SRC_DIR)/cardume.c
FIFO_C = $(SRC_DIR)/fifo.c
MAIN_C = $(SRC_DIR)/main.c
MUNDO_C = $(SRC_DIR)/mundo.c
POSICAO_C = $(SRC_DIR)/posicao.c
SEMAPHORE_C = $(SRC_DIR)/semaphore.c
PARAMETROS_C = $(SRC_DIR)/parametros.c
SHARED_C = $(SRC_DIR)/shared.c
UTIL_C = $(SRC_DIR)/util.c

# Lists

_OBJECTS := barco.o capitao.o cardume.o fifo.o main.o mundo.o posicao.o semaphore.o shared.o util.o parametros.o
OBJECTS  := $(patsubst %, $(OBJ_DIR)/%, $(_OBJECTS))


# MAIN

all: $(TARGET)

$(TARGET): $(OBJECTS) 
	$(CC) $(CFLAGS) $(OBJECTS) -o $(TARGET) $(LIBS)

$(OBJ_DIR)/barco.o: $(BARCO_C) $(BARCO_H) $(PARAMETROS_H) $(POSICAO_H) $(MUNDO_H) $(SEMAPHORE_H) $(CARDUME_H) $(UTIL_H) $(SHARED_H) $(UTIL_H)
	$(CC) $(CFLAGS) -c $(BARCO_C) -o $(OBJ_DIR)/barco.o

$(OBJ_DIR)/capitao.o: $(CAPITAO_C) $(CAPITAO_H) $(MUNDO_H) $(SEMAPHORE_H) $(BARCO_H)
	$(CC) $(CFLAGS) -c $(CAPITAO_C) -o $(OBJ_DIR)/capitao.o

$(OBJ_DIR)/cardume.o: $(CARDUME_C) $(CARDUME.H) $(PARAMETROS_H) $(MUNDO_h) $(SEMAPHORE_H) $(UTIL_H) $(SHARED_H)
	$(CC) $(CFLAGS) -c $(CARDUME_C) -o $(OBJ_DIR)/cardume.o

$(OBJ_DIR)/fifo.o: $(FIFO_C) $(FIFO_H)
	$(CC) $(CFLAGS) -c $(FIFO_C) -o $(OBJ_DIR)/fifo.o

$(OBJ_DIR)/mundo.o: $(MUNDO_C) $(MUNDO_H) $(BARCO_H) $(CARDUME_H) $(UTIL_H) $(SEMAPHORE_H) $(SHARED_H)
	$(CC) $(CFLAGS) -c $(MUNDO_C) -o $(OBJ_DIR)/mundo.o

$(OBJ_DIR)/main.o: $(MAIN_C) $(CAPITAO_H) $(BARCO_H) $(CARDUME_H) $(MUNDO_H) $(SEMAPHORE_H)
	$(CC) $(CFLAGS) -c $(MAIN_C) -o $(OBJ_DIR)/main.o

$(OBJ_DIR)/posicao.o: $(POSICAO_C) $(POSICAO_H)
	$(CC) $(CFLAGS) -c $(POSICAO_C) -o $(OBJ_DIR)/posicao.o

$(OBJ_DIR)/semaphore.o: $(SEMAPHORE_C) $(SEMAPHORE.H)
	$(CC) $(CFLAGS) -c $(SEMAPHORE_C) -o $(OBJ_DIR)/semaphore.o

$(OBJ_DIR)/shared.o: $(SHARED_C) $(SHARED_H)
	$(CC) $(CFLAGS) -c $(SHARED_C) -o $(OBJ_DIR)/shared.o

$(OBJ_DIR)/util.o: $(UTIL_C) $(UTIL_H)
	$(CC) $(CFLAGS) -c $(UTIL_C) -o $(OBJ_DIR)/util.o

$(OBJ_DIR)/parametros.o: $(PARAMETROS_C) $(PARAMETROS_H)
	$(CC) $(CFLAGS) -c $(PARAMETROS_C) -o $(OBJ_DIR)/parametros.o

# Clean_objects

.PHONY: clean
clean: 
	rm -f $(OBJECTS) $(TARGET)

# Delete_temps

.PHONY: delete
delete: 
	rm -f *~

# Wipe_executable

.PHONY: wipe
wipe: 
	rm -f $(TARGET)

# Zip_source_code

DATE = $(shell date +"%Y%m%d")
compress:
	zip $(TEST_DIR)/pesca45$(DATE).zip -r $(SRC_DIR) $(INC_DIR)




