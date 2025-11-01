# Visualization in Python – The gm/Id Design Methodology using Ngspice Simulation Data 

## Screenshot from Xschem
![Xschem Screenshot](https://github.com/user-attachments/assets/c884d639-d1b8-49b2-ba03-58585f53248f)

---

## Ngspice Command
```spice
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
```

## gm/Id Curve

<img width="1200" height="1000" alt="plot" src="https://github.com/user-attachments/assets/35b8e722-2ee7-4111-9ea9-29226d2e9477" />

## gm/Id vs. Vov with Parameter ft

<img width="640" height="480" alt="plot_gm_id_vov_ft" src="https://github.com/user-attachments/assets/08cfd15d-cf74-4b71-ab47-9c842be984b0" />

## gm/Id vs. Square Law Equation - Error Bars

<img width="800" height="600" alt="plot_gm_id_square_law_error" src="https://github.com/user-attachments/assets/39c23c92-ea2f-4ea4-a8c5-5381d3de8eb4" />

## Heatmap W/L with respect to ft

<img width="1000" height="800" alt="plot_w_l_ft" src="https://github.com/user-attachments/assets/ff4ad477-0183-44c6-b2bf-422539f082b1" />
