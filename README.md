# Visualisierungsmöglichkeiten mit Python – Auswertung von Ngspice-Simulationsdaten im Rahmen der gm/Id-Designmethodik

Screenshot from Ngspice
<img width="1366" height="768" alt="Screenshot From 2025-10-25 10-36-44" src="https://github.com/user-attachments/assets/c884d639-d1b8-49b2-ba03-58585f53248f" />

###
Ngspice Command
name=SPICE only_toplevel=false value="
.control
save all

set color0=white
set color1=black

save @n.xm1.nsg13_lv_nmos[ids]
save @n.xm1.nsg13_lv_nmos[gm]
save @n.xm1.nsg13_lv_nmos[id]
save @n.xm1.nsg13_lv_nmos[vgs]
save @n.xm1.nsg13_lv_nmos[vds]
save @n.xm1.nsg13_lv_nmos[vsat]
save @n.xm1.nsg13_lv_nmos[vth]
save @n.xm1.nsg13_lv_nmos[ids]
save @n.xm1.nsg13_lv_nmos[gm]
save @n.xm1.nsg13_lv_nmos[gds]
save @n.xm1.nsg13_lv_nmos[cgg]

*set appendwrite
op
*dc Vds 0.0 2.2 0.1 Vgs 0.0 2.2 0.5
dc Vgs 0.0 2.2 0.1
plot -vds#branch
*plot deriv(-vds#branch)
*let Id_Vgs = -vds#branch

print @n.xm1.nsg13_lv_nmos[ids] @n.xm1.nsg13_lv_nmos[gm] @n.xm1.nsg13_lv_nmos[gds] @n.xm1.nsg13_lv_nmos[cgg] @n.xm1.nsg13_lv_nmos[vth] >> test_1000.txt

*print dc TEMP Id_Vgs >> Id_Vds.txt
*meas dc ids find curr at=1.8
*write test.raw


*show > nmos_tb.txt
.endc
"

###

