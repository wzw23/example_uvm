UVM_HOME = /tools/synopsys/vcs/vcs/Q-2020.03-SP2-7/etc/uvm-1.2
UVM_DIR = +incdir+$(UVM_HOME) +incdir+$(UVM_HOME)/dpi $(UVM_HOME)/uvm.sv $(UVM_HOME)/dpi/uvm_dpi.cc
USER_COMP_OPTS := -full64  -cc gcc-5 -LDFLAGS -Wl,--no-as-needed +v2k -sverilog -timescale=1ns/10ps \
	                -debug_access+all -kdb -fsdb -CFLAGS -DVCS -ntb_opts rvm
comp:
	vcs ${USER_COMP_OPTS} ${UVM_DIR}  *.sv ../../dut/dut.sv -l ./mylog
clean:
	rm -rf  simv.daidir verdi_config_file  verdiLog  *fsdb* *log novas* csrc ucli.key vc_hdrs.h simv
sim:
	./simv -ucli -i my.ucli.cmd
	verdi -dbdir simv.daidir