import streamlit as st
import datetime
from decimal import Decimal


st.title('AfA Rechner für Wirtschaftsgüter')


def berechne_jahre_afa(anschaffungskosten, nutzungsdauer):
    if nutzungsdauer > 0:
        anschaffungskosten_decimal = Decimal(str(anschaffungskosten))
        jahres_afa = anschaffungskosten_decimal / nutzungsdauer
        return jahres_afa
    else:
        st.error('Nutzungsdauer muss mindestens 1 Jahr betragen')

def bestimme_monat_anschaffung(datum_anschaffung):
    monat_anschaffung = datum_anschaffung.month
    return monat_anschaffung

def berechne_zeitanteilige_afa(jahres_afa, monat_anschaffung):
    zeitanteilige_afa = (jahres_afa / 12) * (12 - monat_anschaffung + 1)
    return zeitanteilige_afa


#Eingaben

anschaffungskosten = st.number_input('Anschaffungskosten: ', value=0)

nutzungsdauer = st.number_input('Nutzungsdauer in Jahren: ', value=1)

datum_anschaffung = st.date_input('Datum der Anschaffung (ggf. bei Montage R 7.4 (1) S.3 beachten): ')


#Berechnungen

jahres_afa = berechne_jahre_afa(anschaffungskosten, nutzungsdauer)

monat_anschaffung = bestimme_monat_anschaffung(datum_anschaffung)

zeitanteilige_afa = berechne_zeitanteilige_afa(jahres_afa, monat_anschaffung)


#Ergebnisanzeige

st.success(f'jährliche AfA: {jahres_afa} €')

st.success(f'zeitanteilige AfA: {zeitanteilige_afa} €')
