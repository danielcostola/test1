architecture := $(shell uname -s)
ifeq ($(architecture),Darwin)
	SWTCH=
else
	SWTCH= -D
endif
SRCdir = `pwd`/..
BLDdir = $(SRCdir)/ebld
COMdir = $(SRCdir)/common
CDBdir = $(SRCdir)/ecdb
DFSdir = $(SRCdir)/edfs
MFSdir = $(SRCdir)/emfs
PDFdir = $(SRCdir)/epdf
VLDdir = $(SRCdir)/evld
PLTdir = $(SRCdir)/eplt
CETCdir = $(SRCdir)/cetc
INCLdir = $(SRCdir)/include
PROG = prj$(EXE)
default: $(PROG)

.SUFFIXES: .o .F .f90
.F.o:
	$(MFC) $(FFLAGS) -c $<
.f90.o:
	$(MFC) $(FFLAGS) -c $<
.o :
	$(MCC) $(FFLAGS) -c $<

MODULE_OBJECTS = h3kmodule.o startup.o aim2_module.o aim2_inputs.o CFC_Module.o cadio_Module.o

OBJECTS = prj.o agtprj.o agtcom.o anlytc.o arrow.o ascii_mat.o basesimp.o \
	  basesimp_inputs.o blcond.o bnlthp.o bpfcom.o bpfcontrl.o bscoeff.o bscoeff_extended.o \
	  bsimsel.o c2fdum.o cadio.o cfdat.o cfdrw.o cfg3dv.o cfgmsc.o cfgrid.o cgd.o \
	  clickonbitmap.o common3dv.o commonclm.o context.o ctlexp.o ctlwrt.o ctprob.o \
	  CDBPlugins.o CDBCommon.o CDBExplore.o\
	  ctread.o DG_controller_menu.o dossupport.o e2eplus.o \
	  e3dviews.o ecasctl.o econstr.o econtrol.o edatabase.o edcasctl.o \
	  edcfd.o edcfg.o edcon.o edcondb.o eddb.o edgeo.o edipv.o editCFC.o edmrt.o \
	  edobs.o edonecon.o edoptic.o edpro.o edspmtl.o edtopol.o edzone.o egeometry.o \
	  egbxml.o egrid.o egtgeom.o emeta.o emfnetw.o emkcfg.o enetmisc.o enetprj.o enetrewr.o \
	  eroper.o esru_misc.o esystem.o exlgrad.o explor.o filelist.o folders.o grmprj.o grmcom.o\
	  ground_temp_mains.o gtopol.o h3k_utils.o hcfmk.o hvacgui.o initalc.o insert.o item.o \
	  maintn.o mcdbscn.o mfcdat.o mfelst.o mfnmsc.o mfprb1.o mfprb2.o mfprb3.o mfrlst.o \
	  mksbem.o MultiYear_climate.o mvalid.o \
	  net2pdf.o newnet.o nwkrewr.o plelevvc.o pltcfg.o pltnet.o predefinedwr.o prescoef.o \
	  predef3dv.o prjdmds.o prjfmk.o prjqa.o psychro.o rcdblist.o read3dv.o readTrnsys.o \
	  rwipv.o rwroam.o rwsbem.o sendd.o sendflt.o senrwl.o sensa.o \
	  setup.o sort.o spmisc.o stndrds.o tdfedit.o tdfile.o tdgraph.o \
	  hvacinput.o matpol.o inside.o \
	  PltDummy.o

MODULES = aim2.mod aim2_calcdata.mod aim2_h2k_dummy.mod aim2_inputdata.mod aim2_inputs.mod \
	  aim2_inputs_inputdata.mod start_up.mod parse_command_line.mod h3kmodule.mod \
          CFC_Module.mod cadio_Module.mod

ifeq ($(FMIarg),enableFMI)
	FMI_OBJECTS = FMIcom.o FMIprj.o
else
	FMI_OBJECTS = FMIcom.o FMIprj_dummy.o
endif
ALL_FMI_OBJECTS = FMIcom.o FMIprj.o FMIprj_dummy.o


$(PROG): $(MODULE_OBJECTS) $(FMI_OBJECTS) $(OBJECTS)
	$(MFC) $(LD_FLAGS) -o $(PROG) $(FFLAGS) $(MODULE_OBJECTS) $(FMI_OBJECTS) $(OBJECTS) $(ULIBS) $(BUILD_OPTIONS)

anlytc.F:
	rm -f anlytc.F
	ln -s $(VLDdir)/anlytc.F .
arrow.F:
	rm -f arrow.F
	ln -s $(COMdir)/arrow.F .
ascii_mat.F:
	rm -f ascii_mat.F
	ln -s $(COMdir)/ascii_mat.F .
basesimp.F:
	rm -f basesimp.F
	ln -s $(BLDdir)/basesimp.F .
bscoeff.F:
	rm -f bscoeff.F
	ln -s $(BLDdir)/bscoeff.F .
bscoeff_extended.F:
	rm -f bscoeff_extended.F
	ln -s $(CETCdir)/bscoeff_extended.F .
bsimsel.F:
	rm -f bsimsel.F
	ln -s $(COMdir)/bsimsel.F .
CDBPlugins.F:
	rm -f CDBPlugins.F
	ln -s $(CDBdir)/CDBPlugins.F .
CDBCommon.F:
	rm -f CDBCommon.F
	ln -s $(CDBdir)/CDBCommon.F .
CDBExplore.F:
	rm -f CDBExplore.F
	ln -s $(CDBdir)/CDBExplore.F .
c2fdum.F:
	rm -f c2fdum.F
	ln -s $(COMdir)/c2fdum.F .
CFC_Module.f90:
	rm -f CFC_Module.f90
	ln -s $(BLDdir)/CFC_Module.f90 .
cfdat.F:
	rm -f cfdat.F
	ln -s $(DFSdir)/cfdat.F .
cfdrw.F:
	rm -f cfdrw.F
	ln -s $(COMdir)/cfdrw.F .
cfgmsc.F:
	rm -f cfgmsc.F
	ln -s $(PDFdir)/cfgmsc.F .
cfgrid.F:
	rm -f cfgrid.F
	ln -s $(COMdir)/cfgrid.F .
cgd.F:
	rm -f cgd.F
	ln -s $(DFSdir)/cgd.F .
common3dv.F:
	rm -f common3dv.F
	ln -s $(COMdir)/common3dv.F .
commonclm.F:
	rm -f commonclm.F
	ln -s $(COMdir)/commonclm.F .
ctlexp.F:
	rm -f ctlexp.F
	ln -s $(COMdir)/ctlexp.F .
ctlwrt.F:
	rm -f ctlwrt.F
	ln -s $(COMdir)/ctlwrt.F .
ctprob.F:
	rm -f ctprob.F
	ln -s $(COMdir)/ctprob.F .
ctread.F:
	rm -f ctread.F
	ln -s $(COMdir)/ctread.F .
dossupport.F:
	rm -f dossupport.F
	ln -s $(COMdir)/dossupport.F .
e3dviews.F:
	rm -f e3dviews.F
	ln -s $(COMdir)/e3dviews.F .
ecasctl.F:
	rm -f ecasctl.F
	ln -s $(COMdir)/ecasctl.F .
econstr.F:
	rm -f econstr.F
	ln -s $(COMdir)/econstr.F .
econtrol.F:
	rm -f econtrol.F
	ln -s $(COMdir)/econtrol.F .
edatabase.F:
	rm -f edatabase.F
	ln -s $(COMdir)/edatabase.F .
egeometry.F:
	rm -f egeometry.F
	ln -s $(COMdir)/egeometry.F .
egrid.F:
	rm -f egrid.F
	ln -s $(COMdir)/egrid.F .
egtgeom.F:
	rm -f egtgeom.F
	ln -s $(COMdir)/egtgeom.F .
emfnetw.F:
	rm -f emfnetw.F
	ln -s $(COMdir)/emfnetw.F .
emkcfg.F:
	rm -f emkcfg.F
	ln -s $(COMdir)/emkcfg.F .
enetmisc.F:
	rm -f enetmisc.F
	ln -s $(COMdir)/enetmisc.F .
enetrewr.F:
	rm -f enetrewr.F
	ln -s $(COMdir)/enetrewr.F .
eroper.F:
	rm -f eroper.F
	ln -s $(COMdir)/eroper.F .
esru_misc.F:
	rm -f esru_misc.F
	ln -s $(COMdir)/esru_misc.F .
esystem.F:
	rm -f esystem.F
	ln -s $(COMdir)/esystem.F .
exlgrad.F:
	rm -f exlgrad.F
	ln -s $(CETCdir)/exlgrad.F .
filelist.F:
	rm -f filelist.F
	ln -s $(COMdir)/filelist.F .
h3k_utils.F:
	rm -f h3k_utils.F
	ln -s $(CETCdir)/h3k_utils.F .
initalc.F:
	rm -f initalc.F
	ln -s $(COMdir)/initalc.F .
item.F:
	rm -f item.F
	ln -s $(COMdir)/item.F .
mcdbscn.F:
	rm -f mcdbscn.F
	ln -s $(COMdir)/mcdbscn.F .
mfcdat.F:
	rm -f mfcdat.F
	ln -s $(MFSdir)/mfcdat.F .
mfelst.F:
	rm -f mfelst.F
	ln -s $(MFSdir)/mfelst.F .
mfnmsc.F:
	rm -f mfnmsc.F
	ln -s $(PDFdir)/mfnmsc.F .
mfrlst.F:
	rm -f mfrlst.F
	ln -s $(MFSdir)/mfrlst.F .
MultiYear_climate.F:
	rm -f MultiYear_climate.F
	ln -s $(COMdir)/MultiYear_climate.F .
mvalid.F:
	rm -f mvalid.F
	ln -s $(VLDdir)/mvalid.F .
net2pdf.F:
	rm -f net2pdf.F
	ln -s $(PDFdir)/net2pdf.F .
newnet.F:
	rm -f newnet.F
	ln -s $(PDFdir)/newnet.F .
nwkrewr.F:
	rm -f nwkrewr.F
	ln -s $(COMdir)/nwkrewr.F .
plelevvc.F:
	rm -f plelevvc.F
	ln -s $(COMdir)/plelevvc.F .
pltcfg.F:
	rm -f pltcfg.F
	ln -s $(COMdir)/pltcfg.F .
psychro.F:
	rm -f psychro.F
	ln -s $(COMdir)/psychro.F .
rcdblist.F:
	rm -f rcdblist.F
	ln -s $(COMdir)/rcdblist.F .
rwipv.F:
	rm -f rwipv.F
	ln -s $(COMdir)/rwipv.F .
rwroam.F:
	rm -f rwroam.F
	ln -s $(COMdir)/rwroam.F .
rwsbem.F:
	rm -f rwsbem.F
	ln -s $(COMdir)/rwsbem.F .
senrwl.F:
	rm -f senrwl.F
	ln -s $(COMdir)/senrwl.F .
sort.F:
	rm -f sort.F
	ln -s $(COMdir)/sort.F .
spmisc.F:
	rm -f spmisc.F
	ln -s $(COMdir)/spmisc.F .
stndrds.F:
	rm -f stndrds.F
	ln -s $(VLDdir)/stndrds.F .
startup.F:
	rm -f startup.F
	ln -s $(COMdir)/startup.F .
tdfile.F:
	rm -f tdfile.F
	ln -s $(COMdir)/tdfile.F .
aim2_module.F:
	rm -f aim2_module.F
	ln -s $(BLDdir)/aim2_module.F .
DG_controller_menu.F:
	rm -f DG_controller_menu.F
	ln -s $(CETCdir)/DG_controller_menu.F .
ground_temp_mains.F:
	rm -f ground_temp_mains.F
	ln -s $(BLDdir)/ground_temp_mains.F .
hvacinput.F:
	rm -f hvacinput.F
	ln -s $(CETCdir)/hvacinput.F .
PltDummy.F:
	rm -f PltDummy.F
	ln -s $(PLTdir)/PltDummy.F .

readTrnsys.F:
	rm -f readTrnsys.F
	ln -s $(COMdir)/readTrnsys.F .
h3kmodule.f90:
	rm -f h3kmodule.f90
	ln -s $(CETCdir)/h3kmodule.f90 .
FMIcom.F:
	rm -f FMIcom.F
	ln -s $(COMdir)/FMIcom.F .
matpol.F:
	rm -f matpol.F
	ln -s $(COMdir)/matpol.F .
inside.F:
	rm -f inside.F
	ln -s $(COMdir)/inside.F .
agtcom.F:
	rm -f agtcom.F
	ln -s $(COMdir)/agtcom.F .
grmcom.F:
	rm -f grmcom.F
	ln -s $(COMdir)/grmcom.F .

strip:
	strip $(PROG)

install:
	install $(SWTCH) $(PROG) $(ESPBinDir)/$(PROG)

clean:
	rm -f core $(PROG) $(PROG).exe $(MODULE_OBJECTS) $(OBJECTS) $(ALL_FMI_OBJECTS) $(MODULES) \
	agtcom.F anlytc.F aim2_module.F arrow.F ascii_mat.F basesimp.F bscoeff.F bscoeff_extended.F \
	bsimsel.F c2fdum.F cfdat.F cfdrw.F cfgmsc.F \
	cfgrid.F cgd.F common3dv.F commonclm.F ctlexp.F ctlwrt.F ctprob.F ctread.F DG_controller_menu.F \
	CDBPlugins.F CDBCommon.F CDBExplore.F \
	exlgrad.F dossupport.F e3dviews.F ecasctl.F econstr.F econtrol.F \
	edatabase.F egeometry.F egrid.F egtgeom.F emfnetw.F emkcfg.F enetmisc.F enetrewr.F \
	eroper.F esru_misc.F esystem.F filelist.F grmcom.F ground_temp_mains.F h3k_utils.F initalc.F \
	hvacinput.F item.F mcdbscn.F mfcdat.F mfelst.F mfnmsc.F mfrlst.F MultiYear_climate.F mvalid.F \
	net2pdf.F newnet.F nwkrewr.F plelevvc.F pltcfg.F psychro.F rcdblist.F rwipv.F rwroam.F \
	rwsbem.F senrwl.F sort.F spmisc.F stndrds.F startup.F tdfile.F matpol.F inside.F \
	readTrnsys.F PltDummy.F h3kmodule.f90 FMIcom.F CFC_Module.f90 cfc_module.mod \
	cadio_module.mod

distclean: clean

uninstall:
	-rm -f $(ESPBinDir)/$(PROG)
	
.PHONY: clean install default strip uninstall distclean
