# /*********************************************************************
#  * Copyright (C) 2015, International Business Machines Corporation
#  * All Rights Reserved
#  ********************************************************************/
#

.PHONY: all clean 

SPLC_FLAGS = --data-directory=data -a -x -pthread -x -fopenmp -t ../ --no-mixed-mode-preprocessing --c++std=c++11
SPLC = $(STREAMS_INSTALL)/bin/sc

SPL_CMD_ARGS ?= 
SPL_MAIN_COMPOSITE = TestDNSPerDomainBatch

all: standalone

standalone:
	spl-make-toolkit -i ../com.ibm.streamsx.anomalyDetection
	$(SPLC) $(SPLC_FLAGS) -T -M $(SPL_MAIN_COMPOSITE) $(SPL_CMD_ARGS)

distributed:
	spl-make-toolkit -i ../com.ibm.streamsx.anomalyDetection
	$(SPLC) $(SPLC_FLAGS) -M $(SPL_MAIN_COMPOSITE) $(SPL_CMD_ARGS)

clean: 
	$(SPLC) $(SPLC_FLAGS) -C -M $(SPL_MAIN_COMPOSITE)

