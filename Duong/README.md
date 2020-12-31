# Dương máy chém viết file python trong thư mục này nhé
U_scr = 0.5
K_scr = 40
T_air = 300
T_top = 350
g = 9.8
p_mean_air = 80
p_air = 100
p_top = 150
input_tuple = (U_scr, K_scr, T_air, T_top, g, p_mean_air, p_air, p_top)
# The tuple order is U_ src, K_Scr , T_air, T_top, gravitational coefficient,p_mean_air, p_air, p_Top


def air_flow_rate(input_tuple):
    U_scr, K_scr, T_air, T_top, g, p_mean_air, p_air, p_top = input_tuple
    return U_scr*K_scr*pow(abs(T_air-T_top), 2/3) + (1-U_scr)*pow((g*(1-U_scr)/(2*p_mean_air))*abs(p_air-p_top), 1/2)


def MC_air_top(air_flow_rate):
    CO2_air = int(input("Please enter the CO2 concentration in air : "))
    CO2_top = int(input("Please enter the CO2 concentration in top :"))
    return air_flow_rate*(CO2_air-CO2_top)


a = air_flow_rate(input_tuple)
print(MC_air_top(a))
