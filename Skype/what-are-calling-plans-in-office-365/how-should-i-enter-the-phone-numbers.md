---
title: "Come devo immettere i numeri telefonici?"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/13/2017
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- ms.lync.lac.PortOrderNumbers
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 28aa24b4-8c81-4327-9752-989ea7540db2
description: "Learn how to set up phone numbers when you port them to Skype for Business. "
---

# Come devo immettere i numeri telefonici?

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la [dichiarazione di non responsabilità](28aa24b4-8c81-4327-9752-989ea7540db2.md#MT_Footer). Per visualizzare la versione inglese dell'articolo, [fare clic qui](https://support.office.com/en-us/article/28aa24b4-8c81-4327-9752-989ea7540db2). 
  
Quando si trasferisce i numeri di telefono, è necessario immetterli nel formato corretto.
  
> [!NOTE]
> Ciascun numero di telefono o intervallo di numeri di telefono deve essere immesso separatamente, uno in ogni riga. 
  
- Durante l'immissione di singoli numeri di telefono:
    
  - Tutti i caratteri speciali verranno ignorati (incluso il trattino "-"). Ad esempio:
    
  - Per un numero a 10 cifre: **&amp;*(425*()(*&amp;4&amp;*())(*250649** sarà corretto in **+14255550649**.
    
  - Per un numero a 11 cifre: **1*()(*&amp;42&amp;*()(*&amp;55550649** sarà corretto in **+14255550649**.
    
  - Tutti i tag di 10 o 11 cifre saranno ignorati. Ad esempio, **<div> 4255551234</div>** diventerà **+14255551234**.
    
  - Il segno "-", la spaziatura e le parentesi verranno ignorati. Ad esempio:
    
  - Per un numero a 10 cifre: **(425) 555-6776** verrà corretto in **+14255556776**.
    
  - Per un numero a 11 cifre: **1(425) 555-6776** verrà corretto in **+14255556776**.
    
  - Tutte le lettere verranno considerate come caratteri speciali e viene ignorate se esiste un numero di telefono 10 o 11 cifre. Per esempio:
    
  - Per un numero a 10 cifre: **14jaosia2reoij05jof55506ajfoj49isdjf** verrà corretto in **+14255550649**.
    
  - Per un numero a 11 cifre: **1ade4jaoda2rfoij05ojof55506dsfoj49if** verrà corretto in **+14255550649**.
    
  - Tutte le combinazioni di caratteri speciali, anche di lingue diverse, verranno corrette. Ad esempio: 
    
  - Per un numero a 10 cifre: **中文4中文2ajj5*（）（*（5()...551345** verrà corretto in **+14555551345**.
    
  - Per un numero a 11 cifre: **中文4中文2$a5*（）（*（5()...55(.1345** verrà corretto in **+14555551345**.
    
  - Se tutti i numeri contengono più di 11 cifre o meno di 10 cifre, vengono evidenziate per l'utente correggere:
    
  - ** 5551245** sarà evidenziato e deve essere corretto.
    
  - **1234567891011** sarà evidenziato e deve essere corretto.
    
  - Vengono evidenziati tutti i numeri composti da più di 11 cifre, con i caratteri speciali, o meno di 10 cifre senza da correggere automaticamente.
    
  - Per un numero di cifre 7 senza caratteri speciali che viene immesso: **123456abcdefg7** verranno evidenziate ed è necessario che deve essere corretta, ma non ignorate le lettere.
    
  - Per un numero di cifre 7 con caratteri speciali che viene immesso: **12345!@#$%^ &amp; * ()-@# $% ^ &amp; * () 7** verranno evidenziate per potere. Non è possibile ignorare i caratteri speciali.
    
- Durante l'immissione di un intervallo di numeri di telefono:
    
  - Sono consentiti solo due numeri di telefono. Il numero inferiore dovrà essere il primo numero dell'intervallo.
    
  - Tutti i caratteri speciali (ad eccezione il trattino "-") vengono considerate come numeri singoli. Ad esempio, **(425) 555 0 &amp; * (123-(1425) 5557899nm** verranno corretti in **+14255550123 - +13202040659**.
    
  - La "-" viene utilizzato per separare solo i due numeri. Non è supportata per includere più "-" nell'intervallo di numeri. Ad esempio:, **(425) 555-0649-(425) 555-1115** devono essere immesse come **(425) 5550649 - (425) 5551115**.
    
 **Per istruzioni dettagliate complete, vedere [Trasferire i numeri di telefono a Office 365](transfer-phone-numbers-to-office-365.md).**
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  
## Vedere anche
<a name="MT_Footer"> </a>

#### 

[Termini e condizioni per le chiamate al numero di emergenza](emergency-calling-terms-and-conditions.md)
  
[Periodo di chiamata in uscita di conferenze audio](../accessibility-and-regulatory/audio-conferencing-complimentary-dial-out-period.md)

