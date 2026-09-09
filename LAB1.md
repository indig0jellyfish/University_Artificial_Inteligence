Prima varianta, prezentata:
def verifica_cuvant(cuvant):
    tranzitii = {
        "q0": {
            "a": "q0",
            "b": "q1",
            "c": "q2",
            "e": "q3"
        },

        "q1": {
            "b": "q1",
            "c": "q2",
            "e": "q3"
        },

        "q2": {
            "c": "q2",
            "e": "q3"
        }
    }

    stare_curenta = "q0"
    stare_finala = "q3"

    for litera in cuvant:
        # daca exista o tranzitie valida
        if stare_curenta in tranzitii and litera in tranzitii[stare_curenta]:
            stare_curenta = tranzitii[stare_curenta][litera]
        else:
            return False

    return stare_curenta == stare_finala # daca automatul s-a terminat intr-o stare finala


cuvant = input("Introduceti cuvantul: ")

if verifica_cuvant(cuvant):
    print("Cuvantul apartine limbajului")
else:
    print("Cuvantul nu apartine limbajului")

![Diagrama automatului finit](https://drive.google.com/file/d/1Nnbr_Z4DqIMwYruDN0Vk0riEu6fjYMMB/view?usp=sharing)

A doua varianta, corectata:
def verifica_cuvant(cuvant):

    tranzitii = {
        "q0": {
            "a": "q0",
            "b": "q0",
            "c": "q0",
            "e": "q1"
        }
    }

    stare_curenta = "q0"
    stare_finala = "q1"

    for litera in cuvant:

        if stare_curenta in tranzitii and litera in tranzitii[stare_curenta]:
            stare_curenta = tranzitii[stare_curenta][litera]
        else:
            return False

    return stare_curenta == stare_finala


cuvant = input("Introduceti un cuvant: ")

if verifica_cuvant(cuvant):
    print("Cuvantul apartine limbajului.")
else:
    print("Cuvantul NU apartine limbajului.")

![Diagrama automatului finit](https://drive.google.com/file/d/19zcRJaFlA1A2eX-BB0qmb9oXGO5hq9ZY/view?usp=sharing)
