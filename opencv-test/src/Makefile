PROGS     = cv_test 

INSTDIR   = $(prefix)/usr/bin
INSTMODE  = 0755
INSTOWNER = root
INSTGROUP = root


OBJS = cv_test.o
LDLIBS += -lm -lopencv_core -lopencv_highgui \
	   -lopencv_imgproc -lopencv_video

all: $(PROGS)
$(PROGS): $(OBJS)
	$(CXX) $(CFLAGS) $(LDFLAGS) $^ $(LDLIBS) -o $@

%.o: %.c
	$(CXX) -c $(CFLAGS) $^ -o $@

install: $(PROGS)
	$(INSTALL) -d $(INSTDIR)
	$(INSTALL) -m $(INSTMODE) -o $(INSTOWNER) -g $(INSTGROUP) $(PROGS) $(INSTDIR)

clean:
	rm -f $(PROGS) *.o

