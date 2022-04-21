from cgi import print_form
from distutils.command.install_scripts import install_scripts
import sys
import shutil
from termios import ECHOE
from wsgiref.validate import InputWrapper
import xlsxwriter
import os
import glob
import getpass


def mengenoperation():
    global menge1_liste
    global menge2_liste
    menge1_liste = []
    menge2_liste = []
    while True:
        menge1 = input("Gebe ein Objekt der Menge 1 ein. Um die Menge zu beenden, gebe 'quit' ein: ")

        if menge1 == "quit":
            print("Menge 1:")
            print(menge1_liste)
            break

        try:
            menge1int = (int(menge1))
            menge1_liste.append(menge1int)
        except:
            print("Dies ist keine korrekte Eingabe, bitte tätige eine Eingabe, welche eine Zahl ist.")
    
    while True:
        menge2 = input("Gebe ein Objekt der Menge 2 ein um die Menge zu beenden, gebe 'quit' ein: ")
        
        if menge2 == "quit":
            print("Menge 2:")
            print(menge2_liste)
            break

        try:
            menge2int = (int(menge2))
            menge2_liste.append(menge2int)
        except:
            print("Dies ist keine korrekte Eingabe, bitte tätige eine Eingabe, welche eine Zahl ist.")

    #----------------------------------------------------------------------------------------------------
    while True:
        options_mengenoperation = input("Optionen:\n(1) Schnittmenge ∩\n(2) Vereinigungsmenge ∪\n(3) Differenz ∖\n(4) Produktmenge ×:   ")

        if options_mengenoperation == "1":
            print("\n\nSchnittmenge ∩:")

            set1 = set(menge1_liste).intersection(menge2_liste)
            schnittmenge_mengenoperation = "{" + str('; '.join(map(str, menge1_liste))) + "} ∩ {" + str('; '.join(map(str, menge2_liste))) + "} = {" + str('; '.join(map(str, set1))) + "}"

            print(schnittmenge_mengenoperation + "\n\n\n\n\n-----------------------------------")

        elif options_mengenoperation == "2":
            print("\n\nVereinigungsmenge ∪:")

            menge3_liste = menge1_liste + menge2_liste

            vereinigungsmenge_mengenoperation = "{" + str('; '.join(map(str, menge1_liste))) + "} ∪ {" + str('; '.join(map(str, menge2_liste))) + "} = {" + str('; '.join(map(str, menge3_liste))) + "}"

            print("\n\nVereinigungsmenge ∪:")
            print(vereinigungsmenge_mengenoperation + "\n\n\n\n\n-----------------------------------")
    
        elif options_mengenoperation == "3":
            print("\n\nDifferenz ∖:")

            differenz_menge = set(menge1_liste) - set(menge2_liste)

            differenz_mengenoperation = "{" + str('; '.join(map(str, menge1_liste))) + "} ∖ {" + str('; '.join(map(str, menge2_liste))) + "} = {" + str('; '.join(map(str, differenz_menge))) + "}"

            print(differenz_mengenoperation + "\n\n\n\n\n-----------------------------------")

        elif options_mengenoperation == "4":
            print("\n\nProduktmenge ×:")

            produkt_menge = [(x, y) for x in menge1_liste for y in menge2_liste]

            produktmenge_mengenoperation = "{" + str('; '.join(map(str, menge1_liste))) + "} ∖ {" + str('; '.join(map(str, menge2_liste))) + "} = {" + str('; '.join(map(str, produkt_menge))) + "}"

            print(produktmenge_mengenoperation + "\n\n\n\n\n-----------------------------------")



def mengenvergleichen():
    while True:
        global int_1
        global int_2
        int_1 = 0
        int_2 = 0

        while True:
            value_1 = input("Gebe die erste Zahl ein: ")

            try:
                int_1  = int(value_1)
                break
            except:
                print("Dies ist keine korrekte Eingabe, bitte tätige eine Eingabe, welche eine Zahl ist.")

        while True:
            value_2 = input("Gebe die zweite Zahl ein: ")

            try:
                int_2  = int(value_2)
                break
            except:
                print("Dies ist keine korrekte Eingabe, bitte tätige eine Eingabe, welche eine Zahl ist.")

        if int_1 == int_2:
            print(str(int_1) + " = " + str(int_2))
        
        if int_1 != int_2:
            print(str(int_1) + "  ̸= " + str(int_2))

        if int_1 < int_2:
            print(str(int_1) + " < " + str(int_2))

        if int_1 > int_2:
            print(str(int_1) + " > " + str(int_2))

        if int_1 <= int_2:
            print(str(int_1) + " ≤ " + str(int_2))

        if int_1 >= int_2:
            print(str(int_1) + " ≥ " + str(int_2))



def primzahlen_anzeigen():
    while True:
        global value_1
        value_1 = 0

        while True:
            global startzahl_value
            primzahlen_anzeigen_options = input("Optionen:\n(1) Ist primzahl\n(2) Primzahl von … bis …\n(3) Primfaktorzerlegung\n(4) Teilbarkeitsregeln Primfaktorzerlegung\n(5) Vielfaches bis …\n(6) Teilermenge\n(7) Größter gemeinsamer Teiler\n(8) Kleinstes gemeinsames Vielfaches\nEingabe: ")

            if primzahlen_anzeigen_options == "2":
                global startzahl_value
                global endzahl_value
                global xlsx_write_info
                startzahl_value = 0
                endzahl_value = 0

                prime_list = []
                noprime_list = []
                zahlenmenge_list = []
                zahlengröße = 0
                zahlen_countdown = 0
                xlsx_write_info = False

                while True:
                    startzahl = input("Gebe die Zahl ein, bei der du starten willst, um zum Menu zurückzukehren, gib 'quit' ein: ")
                    
                    if startzahl == "quit":
                        break
                    
                    try:
                        startzahl_value = int(startzahl)
                        
                        if startzahl_value > 0:
                            break
                        else:
                            print("Diese Zahl ist keine natürliche Zahl! Bitte tätige eine Eingabe die größer als null ist!")
                    except:
                        print("Dies ist keine korrekte Eingabe, bitte tätige eine Eingabe, welche eine Zahl ist.")

                while True:
                    endzahl = input("Gebe die Zahl ein, bei der du aufhören willst, um zum Menu zurückzukehren, gib 'quit' ein: ")

                    if startzahl == "quit":
                        break

                    try:
                        endzahl_value = int(endzahl) + 1
                        
                        if endzahl_value > 0:
                            if endzahl_value > startzahl_value:
                                break
                            else:
                                print("Diese Zahl ist kleiner als die Startzahl, bitte gebe eine größere Zahl ein!")
                        else:
                            print("Diese Zahl ist keine natürliche Zahl! Bitte tätige eine Eingabe die größer als null ist!")
                    except:
                        print("Dies ist keine korrekte Eingabe, bitte tätige eine Eingabe, welche eine Zahl ist.")
                
                while True:
                    xlsx_write = input("\n\nWillst du die Werte in einer Excel Datei (xlsx) Datei speichern? (y/n)\n")

                    if xlsx_write == "y":
                        xlsx_write_info = True
                        break
                    elif xlsx_write == "n":
                        xlsx_write = False
                        break
                    else:
                        print("Dies ist keine korrekte Eingabe, bitte tätigen sie eine legitime Eingabe")

                zahlengröße = endzahl_value - startzahl_value
                
                if (endzahl_value - startzahl_value) >= 10000:
                        print("Info: Die Berechnung wird etwas Zeit in Anspruch nehmen!")

                def is_prime(n):
                    if n <= 1:
                        return False
                    for i in range(2,n):
                        if n % i == 0:
                            return False
                    return True
                size = shutil.get_terminal_size()
                for i in range(size.lines):
                        print("\n")
                
                j = 1
                def printProgressBar(value,label):
                    n_bar = size.columns - 24 #size of progress bar
                    global j
                    max = zahlengröße
                    j= value/max
                    sys.stdout.write('\r')
                    bar = '█' * int(n_bar * j)
                    bar = bar + '-' * int(n_bar * (1-j))

                    sys.stdout.write(f"{label.ljust(10)} | [{bar:{n_bar}s}] {int(100 * j)}% ")
                    sys.stdout.flush()
                
                for n in range(startzahl_value, endzahl_value):
                    if is_prime(n) == True:
                        prime_list.append(n)
                    else:
                        noprime_list.append(n)
                    if zahlengröße > 100:
                        printProgressBar(j + n ,"Vortschritt")
                    elif zahlengröße <= 100:
                        printProgressBar(startzahl_value + 1, "Vortschritt")
                
                for i in range(startzahl_value, endzahl_value):
                    zahlenmenge_list.append(i)
                    zahlen_countdown += 1

                print("\n\n\nZahlenmenge: {" + str('; '.join(map(str, zahlenmenge_list))) + "}\n\nPrimzahlen: {" + str('; '.join(map(str, prime_list))) + "}\n\nNicht-Primzahlen: {" + str('; '.join(map(str, noprime_list))) + "}")

                print("\n\nInfo: Bei keinen Datenmengen, kann es zu Abweichungen bei der Vortschrittsanzeige kommen, dies beträchtigt aber nicht die Ergebnissmengen!")

                if xlsx_write_info == True:
                    print("Wrinting .xlsx …")
                    path_of_user = "/Users/" + getpass.getuser()
                    print(path_of_user)
                    
                    directories = glob.glob(path_of_user + "/")
                    print(directories)

                    for i in range(1, 100000):
                        global path_workbook_file
                        path_workbook_file = "/Users/" + str(getpass.getuser()) + "/" + str(i) + ".xlsx"
                        if os.path.exists(path_workbook_file) == False:
                            break
                        else:
                            print(path_workbook_file)
                
                    print("ready")
                    #create xlsx file
                    workbook = xlsxwriter.Workbook(path_workbook_file)
                    worksheet = workbook.add_worksheet()
                    worksheet.set_column('A:A', 20) # Widen the first column to make the text clearer.
                    worksheet.set_column('B:B', 20)
                    worksheet.set_column('C:C', 20)
                    bold = workbook.add_format({'bold': True}) # Add a bold format to use to highlight cells.
                    
                    global row_count_b
                    global row_count_c
                    global row_count_a
                    row_count_c = 1
                    row_count_b = 1
                    row_count_a = 1
                    for n in range(startzahl_value, endzahl_value):
                        if is_prime(n) == True:
                            worksheet.write(row_count_b, 1, n)
                            row_count_b += 1
                        else:
                            worksheet.write(row_count_c, 2, n)
                            row_count_c += 1
                            #noprime_list.append(n)
                    worksheet.write('A1', 'Gesammte Menge')
                    worksheet.write('B1', 'Primzahlen')
                    worksheet.write('C1', 'Nicht-Primzahlen')
                    #worksheet.write(2, 0, 123)

                    for i in range(startzahl_value, endzahl_value):
                        worksheet.write(row_count_a, 0, i)
                        row_count_a += 1
                        #zahlenmenge_list.append(i)
                    
                    workbook.close()
                    print("Done!")

            elif primzahlen_anzeigen_options == "1":
                while True:
                    num_str = input("Gebe eine Zahl ein, um zum Menu zurückzukehren, gib 'quit' ein: ")
                    if num_str == "quit":
                        break
                    try:
                        num = int(num_str)
                        if num > 1:
                            # Iterate from 2 to n / 2
                            for i in range(2, int(num/2)+1):
                                # If num is divisible by any number between
                                # 2 and n / 2, it is not prime
                                if (num % i) == 0:
                                    print(num, " ist keine Primzahl")
                                    break
                            else:
                                print(num, " ist eine Primzahl")
                        
                        else:
                            print(num, " ist keine Primzahl.")
                    except:
                        print("Dies ist keine korrekte Eingabe! Bitte betätige eine korrekte Eingabe!")

            elif primzahlen_anzeigen_options == "3":
                while True:
                    parts_list = []
                    global zerlegung
                    zerlegung = 0
                    zerlegung_str = input("Gebe eine Zahl ein, um zum Menu zurückzukehren, gib 'quit' ein: ")

                    if zerlegung_str == "quit":
                        break

                    try:
                        zerlegung = int(zerlegung_str)
 
                        i = 2
                        while i <= zerlegung:
                            while zerlegung % i == 0:
                                parts_list.append(i)
                                zerlegung = zerlegung / i
                            i = i + 1
                        
                        print(zerlegung_str + " = ", str(' * '.join(map(str, parts_list))))
                    except:
                        print("Dies ist keine korrekte Eingabe! Bitte betätige eine korrekte Eingabe!")

            elif primzahlen_anzeigen_options == "4":
                print("""Eine Zahl ist durch ...
2 teilbar, wenn ihre letzte Ziffer eine 2, 4, 6, 8 oder 0 ist. 3 teilbar, wenn ihre Quersumme durch 3 teilbar ist.
4 teilbar, wenn ihre letzten 2 Stellen durch 4 teilbar sind. 5 teilbar, wenn ihre letzte Stelle eine 5 oder eine 0 ist.
6 teilbar, wenn sie durch 2 und durch 3 teilbar ist.
8 teilbar, wenn ihre letzten 3 Stellen durch 8 teilbar sind. 9 teilbar, wenn ihre Quersumme durch 9 teilbar ist.
10 teilbar, wenn ihre letzte Stelle eine 0 ist.
12 teilbar, wenn sie durch 3 und durch 4 teilbar ist.
15 teilbar, wenn sie durch 3 und durch 5 teilbar ist.
18 teilbar, wenn sie durch 2 und durch 9 teilbar ist.
Die Quersumme einer Zahl, ist die Summe ihrer Ziffern.\n\n\n\n\n\n""")

            elif primzahlen_anzeigen_options == "5":
                vielfaches_continue = 0
                vielfaches = 0
                vielfaches_end = 0
                vielfaches_list = []

                while True:
                    vielfaches_str = input("Gebe eine Zahl ein: ")

                    try:
                        vielfaches = int(vielfaches_str)
                        vielfaches_continue = int(vielfaches_str)
                        break
                    except:
                        print("Dies ist keine korrekte Eingabe! Bitte betätige eine korrekte Eingabe!")
                
                while True:
                    vielfaches_end_str = input("Gebe ein, wie offt das Vielfache gebildet werden soll.\nEingbae: ")

                    try:
                        vielfaches_end = int(vielfaches_end_str)
                        break
                    except:
                        print("Dies ist keine korrekte Eingabe! Bitte betätige eine korrekte Eingabe!")
                
                for i in range(vielfaches_end):
                    vielfaches_list.append(vielfaches)
                    vielfaches += vielfaches_continue
                
                print("\n\n\n\nV(", vielfaches_continue, ") = {", str('; '.join(map(str, vielfaches_list))), "}")

            elif primzahlen_anzeigen_options == "6":
                while True:
                    a=[]
                    teiler_int = 0
                    teiler_str=input("Gebe eine Zahl ein, um zum Menu zurückzukehren, gib 'quit' ein: ")
                    
                    if teiler_str == "quit":
                        break
                    
                    try:
                        teiler_int = int(teiler_str)
                        i=1

                        while i <= teiler_int:
                            if teiler_int%i==0:
                                Teiler=teiler_int//i        
                                a.append(Teiler)
                                i=i+1

                            else:
                                i=i+1
                            
                        a.reverse()
                        print("\n\n\n\nT(",teiler_int,") = {",str('; '.join(map(str, a))),"}")
                    except:
                        print("Dies ist keine korrekte Eingabe! Bitte betätige eine korrekte Eingabe!")
            
            elif primzahlen_anzeigen_options == "7":
                global value_1_int
                global value_2_int
                value_1_int = 0
                value_2_int = 0
                
                while True:
                    value_1_str = input("Gebe die erst Zahl ein, um zum Menu zurückzukehren, gib 'quit' ein: ")

                    if value_1_str == "quit":
                        primzahlen_anzeigen()

                    try:
                        value_1_int = int(value_1_str)
                        break
                    except:
                        print("Dies ist keine korrekte Eingabe! Bitte betätige eine korrekte Eingabe!")
                
                while True:
                    value_2_str = input("Gebe die zweite Zahl ein, um zum Menu zurückzukehren, gib 'quit' ein: ")

                    if value_2_str == "quit":
                        primzahlen_anzeigen()

                    try:
                        value_2_int = int(value_2_str)
                        break
                    except:
                        print("Dies ist keine korrekte Eingabe! Bitte betätige eine korrekte Eingabe!")
                
                if value_1_int == 0:
                    print(value_2_int)
                else:
                    while value_2_int != 0:
                        if value_1_int > value_2_int:
                            value_1_int = value_1_int - value_2_int
                        else:
                            value_2_int = value_2_int - value_1_int
                print('\n\n\nDer größte gemeinsame Teiler ist: ' + str(value_1_int), "\n\n\n")

            elif primzahlen_anzeigen_options == "8":
                value_1_int = 0
                value_2_int = 0

                while True:
                    value_1_str = input("Gebe die erst Zahl ein, um zum Menu zurückzukehren, gib 'quit' ein: ")

                    if value_1_str == "quit":
                        primzahlen_anzeigen()

                    try:
                        value_1_int = int(value_1_str)
                        break
                    except:
                        print("Dies ist keine korrekte Eingabe! Bitte betätige eine korrekte Eingabe!")
                
                while True:
                    value_2_str = input("Gebe die zweite Zahl ein, um zum Menu zurückzukehren, gib 'quit' ein: ")

                    if value_2_str == "quit":
                        primzahlen_anzeigen()

                    try:
                        value_2_int = int(value_2_str)
                        break
                    except:
                        print("Dies ist keine korrekte Eingabe! Bitte betätige eine korrekte Eingabe!")
                
                def kgV(value_1_int, value_2_int):
                        # Variable für Multiplikator
                        m = 1
                        while m > 0:
                            # Variable für Vielfaches
                            lcm = m * value_1_int
                            if lcm % value_2_int == 0:
                                return lcm
                                m = 0
                            m = m + 1
                print("\nDas kleines geminsame Vielfache ist: ", kgV(value_1_int, value_2_int))

            else:
                print("Dies ist keine korrekte Eingabe! Bitte betätige eine korrekte Eingabe!")

def grundrechnungen():
    while True:
        global value_1
        global value_2
        value_1 = 0
        value_2 = 0

        while True:
            grundrechnungen_options = input("(1) Addition\n(2) Subtraktion\n(3) Multiplikation\n(4) Division\nEingabe: ")

            try:
                int(grundrechnungen_options)
                break
            except:
                print("Dies ist keine korrekte Eingabe! Bitte betätige eine korrekte Eingabe!")
        
        while True:
            global value_1_str
            value_1_str = input("Gebe die erste Zahl ein, um zum Menu zurückzukehren, gib 'quit' ein: ")

            if value_1_str == "quit":
                grundrechnungen()
            
            try:
                value_1 = int(value_1_str)
                break
            except:
                print("Dies ist keine korrekte Eingabe! Bitte betätige eine korrekte Eingabe!")

        while True:
            global value_2_str
            value_2_str = input("Gebe die zweite Zahl ein, um zum Menu zurückzukehren, gib 'quit' ein: ")

            if value_2_str == "quit":
                grundrechnungen()
            
            try:
                value_2 = int(value_2_str)
                break
            except:
                print("Dies ist keine korrekte Eingabe! Bitte betätige eine korrekte Eingabe!")        

        if grundrechnungen_options == "1":
            print(str(value_1), " + ", str(value_2), " = ", str(value_1 + value_2))
        
        elif grundrechnungen_options == "2":
            print(str(value_1), " - ", str(value_2), " = ", str(value_1 - value_2))
        
        elif grundrechnungen_options == "3":
            print(str(value_1), " / ", str(value_2), " = ", str(value_1 * value_2))
        
        elif grundrechnungen_options == "4":
            print(str(value_1), " * ", str(value_2), " = ", str(value_1 / value_2))


def grundrechenregeln():
    global value_1
    value_1 = 0
    global value_2
    value_2 = 0
    global value_1_str
    global value_2_str
    def get_value_12():
        while True:
            global value_1
            global value_1_str
            value_1_str = input("Gebe die erste Zahl ein, um zum Menu zurückzukehren, gib 'quit' ein: ")

            if value_1_str == "quit":
                grundrechenregeln()

            try:
                value_1 = int(value_1_str)
                break
            except:
                print("Dies ist keine korrekte Eingabe! Bitte betätige eine korrekte Eingabe!")
            
        while True:
            global value_2
            global value_2_str
            value_2_str = input("Gebe die zweite Zahl ein, um zum Menu zurückzukehren, gib 'quit' ein: ")

            if value_2_str == "quit":
                grundrechenregeln()
                
            try:
                value_2 = int(value_2_str)
                break
            except:
                print("Dies ist keine korrekte Eingabe! Bitte betätige eine korrekte Eingabe!")

    while True:
        grundrechenregeln_options = input("(1) Kommutativgesetz\n(2) Assoziativgesetz\n(3) Distributivgesetz\n(4)Rechenreihenfolge\nEingabe: ")
        
        if grundrechenregeln_options == "4":
            print("\nBeispiel zu der Rechenreihenfolge, um die genauen Regeln nachzulesen, wähle das Menue 'Theorie':\n100 - 40 - 5 · (42 - 5 · 2^3)^2 =\n100 - 40 - 5 · (42 - 5 · 8)^2 =\n100 - 40 - 5 · (42 - 40)^2 =\n100 - 40 - 5 · 2^2 =\n100 - 40 - 5 · 4 =\n100 - 40 - 20 =\n60 - 20 =\n40")
            grundrechenregeln()

        try:
            cvalue = int(grundrechenregeln_options)
        except:
            print("Dies ist keine korrekte Eingabe! Bitte betätige eine korrekte Eingabe!")
            grundrechenregeln()
        
        if cvalue == 1:
            get_value_12()

            print(value_1_str, " * ", value_2_str, " = ", value_2_str, " * ", value_1_str)

        elif cvalue == 2 or 3:
            get_value_12()

            while True:
                value_3_str = input("Gebe die dritte Zahl ein, um zum Menu zurückzukehren, gib 'quit' ein: ")

                if value_3_str == "quit":
                    grundrechenregeln()

                try:
                    int(value_3_str)
                    break
                except:
                    print("Dies ist keine korrekte Eingabe! Bitte betätige eine korrekte Eingabe!")

            if cvalue == 2:
                print("(", str(value_1), " * ", str(value_2), ") * ", value_3_str, " = ", str(value_1), " * (", str(value_2), value_3_str, ")\n"\
                    ,"(" ,str(value_1), " + ", str(value_2), ") + ", value_3_str, " = ", str(value_1), " + (", str(value_2), " + ", value_3_str, ")")


def vorzeichenregeln():
    vorzeichenregeln_options = input("(1) Vorzeichen und Klammern\n(2) Multiplikation\n(3) Division\n(4) Betrag einer Zahl\nEingabe:")

    if vorzeichenregeln_options == "1":
        value_1_str = input("Gebe eine Zahl ein, um zum Menue zurückzukehren, gib quit' ein: ")

        if value_1_str == "quit":
            vorzeichenregeln()
        
        while True:
            try:
                int(value_1_str)
                if int(value_1_str) <= 0:
                    print("Die Eingabe draf nicht kleiner, oder gelich null sein!")
                    value_1_str = input("Gebe eine Zahl ein, um zum Menue zurückzukehren, gib quit' ein: ")
                else:
                    break
            except:
                print("Dies ist keine korrekte Eingabe! Bitte betätige eine korrekte Eingabe!")

        print("+(+", value_1_str, ") = +", value_1_str, "\n"\
            "+(-", value_1_str, ") = -", value_1_str, "\n"\
                "-(+", value_1_str, ") = -", value_1_str, "\n"\
                    "-(-", value_1_str, ") = +", value_1_str)
        vorzeichenregeln()

    elif vorzeichenregeln_options == "2" or "3":
        while True:
            while True:
                value_1_str = input("Gebe die erste Zahl ein, um zum Menu zurückzukehren, gib 'quit' ein: ")

                if value_1_str == "quit":
                    vorzeichenregeln()
                
                try:
                    int(value_1_str)
                    if int(value_1_str) <= 0:
                        print("Die Eingabe draf nicht kleiner, oder gelich null sein!")
                    else:
                        break
                except:
                    print("Dies ist keine korrekte Eingabe! Bitte betätige eine korrekte Eingabe!")
            
            while True:
                value_2_str = input("Gebe die zweite Zahl ein, um zum Menu zurückzukehren, gib 'quit' ein: ")

                if value_2_str == "quit":
                    vorzeichenregeln()

                try:
                    int(value_2_str)
                    if int(value_2_str) <= 0:
                        print("Die Eingabe draf nicht kleiner, oder gelich null sein!")
                    else:
                        break
                except:
                    print("Dies ist keine korrekte Eingabe! Bitte betätige eine korrekte Eingabe!")

            if vorzeichenregeln_options == "2":
                print("\n +", value_1_str, " * (+", value_2_str, ") = +", str(int(value_1_str) * int(value_2_str)), "\n",\
                    "-", value_1_str, " * (-", value_2_str, ") = +", str(int(value_1_str) * int(value_2_str)), "\n",\
                        "+", value_1_str, " * (-", value_2_str, ") = -", str(int(value_1_str) * int(value_2_str)), "\n",\
                            "-", value_1_str, " * (+", value_2_str, ") = -", str(int(value_1_str) * int(value_2_str)))

            elif vorzeichenregeln_options == "3":
                print("\n +", value_1_str, " / +", value_2_str, " = +", str(int(value_1_str) / int(value_2_str)), "\n",\
                    "-", value_1_str, " / -", value_2_str, " = +", str(int(value_1_str) / int(value_2_str)), "\n",\
                        "+", value_1_str, " / +", value_2_str, " = -", str(int(value_1_str) / int(value_2_str)), "\n",\
                            "-", value_1_str, " / +", value_2_str, " = -", str(int(value_1_str) / int(value_2_str)))

    elif vorzeichenregeln_options == "4":
        while True:
            value_str = input("Gebe eine Zahl ein, um zum Menu zurückzukehren, gib 'quit' ein: ")

            if value_str == "quit":
                vorzeichenregeln()

            try:
                int(value_str)
                if int(value_str) <= 0:
                    print("Die Eingabe draf nicht kleiner, oder gelich null sein!")
                else:
                    break
            except:
                print("Dies ist keine korrekte Eingabe! Bitte betätige eine korrekte Eingabe!")
            
            print("|-", value_str, "| = ", value_str, "\n"\
                "|", value_str, "| = ", value_str)


def brüche():
    brüche_options = input("(1) Erweitern von Brüchen\n(2) Kürzen von Brüchen\n(3) Addition gleichnamiger Brüche\n(4) Subtraktion gleichnamiger Brüche\n(5) Addition ungleichnamiger Brüche\n(6) Subtraktion ungleichnamiger Brüche\n(7) Multiplikation von Brüchen\n(8) Division von Brüchen\nEingabe: ")

    if brüche_options == "1" or "2" or "3" or "4":
        
        while True:
            value_1_str = input("Gebe die erste Zahl ein, um zum Menu zurückzukehren, gib 'quit' ein: ")

            if value_1_str == "quit":
                brüche()
            
            try:
                int(value_1_str)
                break
            except:
                print("Dies ist keine korrekte Eingabe! Bitte betätige eine korrekte Eingabe!")
        
        while True:
            value_2_str = input("Gebe die zweite Zahl ein, um zum Menu zurückzukehren, gib 'quit' ein: ")

            if value_2_str == "quit":
                brüche()

            try:
                int(value_1_str)

                if int(value_2_str) == 0:
                    print("Die Eingabe draf nicht gleich null sein!")
                else:
                    break
            except:
                print("Dies ist keine korrekte Eingabe! Bitte betätige eine korrekte Eingabe!")

        while True:
            value_3_str = input("Gebe die dritte Zahl ein, um zum Menu zurückzukehren, gib 'quit' ein: ")
            
            if value_3_str == "quit":
                brüche()

            try:
                int(value_3_str)
                
                if int(value_3_str) == 0:
                    print("Die Eingabe draf nicht gleich null sein!")
                else:
                    break
            except:
                print("Dies ist keine korrekte Eingabe! Bitte betätige eine korrekte Eingabe!")

        if brüche_options == "1":
            print(value_1_str, "/", value_2_str, " = (", value_1_str, "*", value_3_str,")/(", value_2_str, "*", value_3_str, ") = ", str((int(value_1_str) * int(value_3_str))), "/", str(int(value_2_str) * int(value_3_str)))
        
        elif brüche_options == "2":
            print(value_1_str, "/", value_2_str, " = (", value_1_str, "/", value_3_str,")/(", value_2_str, "/", value_3_str, ") = ", str((int(value_1_str) / int(value_3_str))), "/", str(int(value_2_str) / int(value_3_str)))
        
        elif brüche_options == "3":
            print(value_1_str, "/", value_3_str, " + ", value_2_str, "/", value_3_str, " = (", value_1_str, " + ", value_2_str, ")/", value_3_str, " = ", str(int(value_1_str) + int(value_2_str)), "/", value_3_str)

        elif brüche_options == "4":
            print(value_1_str, "/", value_3_str, " - ", value_2_str, "/", value_3_str, " = (", value_1_str, " - ", value_2_str, ")/", value_3_str, " = ", str(int(value_1_str) - int(value_2_str)), "/", value_3_str)
    
    brüche()


#-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

def menue():
    print("Diese Anwendung ist zurzeit noch in der Entwicklung und ist daher fehleranfällig in der benutzung. Es sind aber keine Ergebnisse verfälscht. Diese Anwenung wurde für MacOS optimirt und kann daher fehler bei dem Export von Excel-Dateien bei anderen Betriebssysthemen wie Windows oder Linux aufweisen. Ich bitte um Verständniss. Auserdem wird es in späteren Versionen auch eine grafisch basierte Version geben.")
    while True:
        auswahl_main = input("Hallo, bitte wähle eine Option aus.\n(1) Algebra\nEingabe:")

        if auswahl_main == "1":
            while True:
                auswahl_algebra = input("Wähle eine Option, um zurückzukehren, gebe 'quit' ein.\n(1) Grundlagen\nEingabe: ")

                if auswahl_algebra == "quit":
                    menue()
                if auswahl_algebra == "1":
                    auswahl_algebra_grundlagen = input("Wähle eine Option, um zurückzukehren, gebe 'quit' ein.\n(1) Mengenoperationen\n(2) Mengen vergleichen\n(3) Primfaktoren - ggT - kgV\n(4) Grundrechnungen\n(5) Grundrechenregeln\n(6) Vorzeichenregeln\n(7) Brüche\nEingabe: ")
                    
                    if auswahl_algebra_grundlagen == "quit":
                        menue()

                    elif auswahl_algebra_grundlagen == "1":
                        mengenoperation()
                    
                    elif auswahl_algebra_grundlagen == "2":
                        mengenvergleichen()

                    elif auswahl_algebra_grundlagen == "3":
                        primzahlen_anzeigen()

                    elif auswahl_algebra_grundlagen == "4":
                        grundrechnungen()

                    elif auswahl_algebra_grundlagen == "5":
                        grundrechenregeln()
                    
                    elif auswahl_algebra_grundlagen == "6":
                        vorzeichenregeln()

                    elif auswahl_algebra_grundlagen == "7":
                        print("Info: Dieses Kapitel wird gerade noch erstellt, so können manche Optionen nicht verfügbar sein!")
                        brüche()
                else:
                    print("Dies ist keine korrekte Eingabe! Bitte betätige eine korrekte Eingabe!")
        else:
             print("Dies ist keine korrekte Eingabe! Bitte betätige eine korrekte Eingabe!")

menue()
