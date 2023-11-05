# Analog-electronics-project

component = input("Enter BJT or MOSFET: ")
if component == "BJT":
    print("1. Fixed bias")
    print("2. Emitter bias")
    print("3. Voltage divider bias")
    print("4. Collector feedback bias")

    choice = int(input("Choose the biasing method (1-4): "))

    if choice == 1: 
        Vcc = float(input("Enter the value of Vcc: "))
        Vbe = float(input("Enter the value of Vbe: "))
        Vce = float(input("Enter the value of Vce: "))
        Ib = float(input("Enter the value of Ib: "))
        Beta = float(input("Enter the value of Beta: "))
        Rb = (Vcc - Vbe) / Ib
        Ic = Beta * Ib
        Rc = (Vcc - Vce) / Ic
        print(f"Rb : {Rb}\nRc : {Rc}")

    elif choice == 2:
        Vcc = float(input("Enter the value of Vcc: "))
        Vbe = float(input("Enter the value of Vbe: "))
        Vce = float(input("Enter the value of Vce: "))
        Ib = float(input("Enter the value of Ib: "))
        Beta = float(input("Enter the value of Beta: "))
        Re = float(input("Enter the value of Re: "))
        Rb = (Vcc - Vbe) - Ib * (Beta + 1) * Re / Ib
        Ic = Ib * Beta
        Rc = Vcc - Vce - (Ic * Re) / Ic
        print(f"Rb : {Rb}\nRc : {Rc}")

    elif choice == 3:
        ETh = float(input("Enter the value of Eth: "))
        Vbe = float(input("Enter the value of Vbe: "))
        Vcc = float(input("Enter the value of Vcc: "))
        Vce = float(input("Enter the value of Vce: "))
        Ib = float(input("Enter the value of Ib: "))
        Beta = float(input("Enter the value of Beta: "))
        Re = float(input("Enter the value of Re: "))
        RTh = ETh - Vbe - (Ib * (Beta + 1)) * Re / Ib
        Ic = Beta * Ib
        Rc = Vcc - Vce - (Ic * Re) / Ic
        print(f"RTh : {RTh}\nRc : {Rc}")

    elif choice == 4:
        Vcc = float(input("Enter the value of Vcc: "))
        Vbe = float(input("Enter the value of Vbe: "))
        Vce = float(input("Enter the value of Vce: "))
        Ib = float(input("Enter the value of Rf: "))
        Beta = float(input("Enter the value of Beta: "))
        Rc = float(input("Enter the value of Rc: "))
        Re = float(input("Enter the value of Re: "))
        Rf = Vcc - Vbe - (Ib * Beta * (Rc + Re)) / Ib
        Ic = Beta * Ib
        Rc = Vcc - Vce - (Ic * Re) / Ic
        print(f"Rf : {Rf}\nRc : {Rc}")

elif component == "MOSFET":
    Vdd = float(input("Enter the value of Vdd: "))
    Id = float(input("Enter the value of Id: "))
    Rd = float(input("Enter the value of Rd: "))
    Rs = float(input("Enter the value of Rs: "))
    Vg = float(input("Enter the value of Vg: "))
    Vds = Vdd - Id * (Rd + Rs)
    Vgs = Vg - (Id * Rs)
    print(f"Vds: {Vds}\nVgs: {Vgs}")