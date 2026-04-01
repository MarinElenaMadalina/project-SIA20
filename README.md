# project-SIA20

Acest folder conține sursele de date utilizate în proiectul de gestiune și detectare a fraudelor bancare.

Overview
Proiectul utilizează surse de date multiple și formate de stocare eterogene pentru a susține integrarea și analiza comportamentului tranzacțional:

Oracle SQL – Date despre clienți și conturi bancare

CSV – Tranzacții cu cardul (set de date pentru detecția fraudelor)

JSON – Jurnal de alerte de securitate și investigații

Data Sources
1. CLIENTS

Type: SQL / Oracle

Description: Baza de date centrală care conține informațiile de identificare ale clienților și cardurile active.

Source: Date generate sintetic pentru simularea mediului bancar core.

Structure: Tabelele CLIENTI (ID, Nume, Prenume, Adresa) și CARDURI (ID_Card, ID_Client, Status).

2. TRANSACTIONS

Type: CSV

Description: Set de date ce conține tranzacții efectuate cu carduri de credit în septembrie 2013 de către deținători europeni.

Source: Kaggle - Credit Card Fraud Detection

Link: https://www.kaggle.com/datasets/jayfaldu/creditcard-fraud-detection

Note: Datele sunt anonimizate prin transformare PCA (V1-V28) și includ variabila țintă Class (1 pentru fraudă).

3. FRAUD_ALERTS

Type: JSON

Description: Jurnal ierarhic care stochează alertele generate automat de sistem pentru tranzacțiile suspecte identified în sursa anterioară.

Source: Fișier de configurare/output al sistemului de monitorizare.

Structure: Obiecte de tip alertă care corelează ID-ul tranzacției cu severitatea și statusul rezoluției (Confirmed/False Positive).

Notes
Aceste surse sunt utilizate în cadrul unei abordări de integrare a datelor eterogene, combinând tehnologii relaționale și fișiere de tip flat-file/document pentru procesarea analitică a riscului de fraudă.
