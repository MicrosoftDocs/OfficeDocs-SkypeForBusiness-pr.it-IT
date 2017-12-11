---
title: "Che cosa sono il routing delle chiamate, gli indirizzi e le posizioni per gli interventi di emergenza?"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/17/2017
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- ms.lync.lac.AddressAndLocation
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
description: "Learn what emergency address, location, and emergency call routing are, and how to plan and assign them to your users. "
---

# Che cosa sono il routing delle chiamate, gli indirizzi e le posizioni per gli interventi di emergenza?

Durante la configurazione dei Piani per chiamate per Office 365, è obbligatorio associare un indirizzo di emergenza a ogni numero di telefono ottenuto o assegnato a un utente per supportare le chiamate di emergenza. L'indirizzo di emergenza deve essere stato creato e convalidato prima di essere assegnato a un numero di telefono. La convalida conferma la corretta formattazione dell'indirizzo di emergenza, che può dunque essere usato dai servizi di emergenza. In via facoltativa, è possibile aggiungere una posizione nell'indirizzo di emergenza per fornire indicazioni più specifiche per l'utente. Ad esempio, la posizione di emergenza potrebbe essere un piano, un'ala o un ufficio collegato a un indirizzo di emergenza specifico. Diversamente dagli indirizzi di emergenza, le posizioni non vengono convalidate.
  
## Che cosa sono gli indirizzi per gli interventi di emergenza?

L'indirizzo di emergenza per i numeri di telefono attivi è obbligatorio, ma il punto specifico in cui diventa obbligatorio dipende dal Paese o area geografica. Negli Stati Uniti, l'indirizzo di emergenza è **obbligatorio** quando un numero viene assegnato a un utente. In altri paesi, come in Europa, Medio Oriente e Africa (EMEA), l'indirizzo di emergenza è **obbligatorio** quando si ottiene il numero di telefono da Office 365 o quando il numero viene trasferito da un altro provider o gestore di servizi.
  
Per indirizzo di emergenza si intende un indirizzo civico, un indirizzo stradale o un indirizzo fisico. Si tratta dell'indirizzo stradale o civico di una sede o ufficio dell'organizzazione, ad esempio  *12345 North Main Street, Redmond, WA 98052*  . Questo indirizzo viene utilizzato per trasmettere le chiamate di emergenza alle autorità appropriate e per agevolare l'individuazione del chiamante. Se la tua azienda ha più di una sede fisica potresti dover fornire più indirizzi di emergenza.
  
La convalida di un indirizzo civico o stradale implica la verifica della legittimità e della corretta formattazione per i servizi di emergenza. Sebbene sia possibile creare e salvare un indirizzo di emergenza non convalidato, gli indirizzi non convalidati non possono essere associati agli utenti. L'indirizzo di emergenza deve essere convalidato e salvato prima di poter essere associato a un utente. Se è necessario apportare una modifica a un indirizzo di emergenza convalidato, occorrerà crearne uno nuovo.
  
## Che cosa sono le posizioni per gli interventi di emergenza?

Le posizioni per gli interventi di emergenza sono associate a un indirizzo per gli interventi di emergenza, al fine di indicare in modo più preciso una posizione fisica all'interno di un edificio. La posizione per gli interventi di emergenza può corrispondere di solito al piano, all'ala dell'edificio o al numero dell'ufficio in cui si trova l'utente. È possibile indicare un numero illimitato di posizioni associate a un indirizzo per gli interventi di emergenza. 
  
Durante l'assegnazione di un indirizzo di emergenza a un utente, si fa in genere riferimento a un ID posizione. Nell'ID posizione è riportato l'indirizzo di emergenza di riferimento (la strada o l'indirizzo civico). Nel caso in cui non sia necessario indicare posizioni all'interno di un edificio, all'indirizzo di emergenza viene associata una posizione predefinita. 
  
## Che cos'è il routing delle chiamate di emergenza?

Gli indirizzi e le posizioni di emergenza sono usati durante il processo di routing delle chiamate di emergenza al centro appropriato per l'inoltro agli operatori dei servizi di emergenza. Quando un utente di Skype for Business chiama un numero di emergenza, il routing della chiamata al centro di raccolta delle chiamate di emergenza (PSAP, Public Safety Answering Point) cambia in base al paese o regione geografica. In alcuni paesi, come Stati Uniti e Regno Unito, le chiamate vengono innanzitutto vagliate per determinare la posizione attuale dell'utente e in seguito inoltrate al centro di emergenza appropriato. In altri paesi e aree geografiche, le chiamate vengono instradate direttamente al centro di emergenza che ha in carico il numero di telefono associato all'utente che effettua la chiamata di emergenza.
  
## Creazione, aggiunta e assegnazione di indirizzi e posizioni per gli interventi di emergenza agli utenti

1. **Configurare le posizioni di emergenza** Il primo passaggio consiste nel pianificare le posizioni di emergenza. In base a tale pianificazione, si stabilisce se siano necessarie posizioni per gli indirizzi di emergenza e, in tal caso, le si specifica. Se ad esempio un'azienda ha 3 edifici, ognuno con 4 piani, probabilmente saranno necessari 3 indirizzi di emergenza, con l'elenco dei piani da 1 a 4 come posizione per ogni edificio.
    
2. **Creare e convalidare le posizioni per gli interventi di emergenza** Il passaggio successivo consiste nel creare e convalidare gli indirizzi per gli interventi di emergenza. Quando crei un indirizzo per gli interventi di emergenza, puoi convalidarlo. Per creare un indirizzo per gli interventi emergenza, vedi[Aggiungere o rimuovere un indirizzo di emergenza per l'organizzazione](add-or-remove-an-emergency-address-for-your-organization.md).
    
    > [!IMPORTANT]
    > La convalida di un indirizzo civico o stradale implica la verifica della legittimità e della corretta formattazione dell'indirizzo. È possibile che un indirizzo di emergenza parzialmente corretto, in cui hai ad esempio digitato erroneamente il nome della città, superi comunque la fase di convalida. Il processo di convalida utilizza tutte le parti di un dato indirizzo per stabilire se contiene informazioni sufficienti a inoltrare la chiamata al centro dei servizi di emergenza più appropriato. In tal caso viene considerato convalidato e può essere assegnato a un numero di telefono. 
  
3. **Ottenere i numeri di telefono** Il passaggio successivo consiste nell'ottenere i numeri di telefono per gli utenti. Puoi eseguire l'operazione ottenendo nuovi numeri di telefono da Office 365 o attraverso la "portabilità" o il trasferimento dei numeri di telefono esistenti in Office 365. Per le istruzioni dettagliate, consulta[Trasferire i numeri di telefono a Office 365](transfer-phone-numbers-to-office-365.md).
    
4. **Assegnare i numeri di telefono** L'ultimo passaggio consiste nel consentire agli utenti di effettuare e ricevere telefonate: a tale scopo, sarà necessario assegnare un numero di telefono a ciascun utente. Per assegnare un numero di telefono, fare riferimento a[Assegnare, modificare o rimuovere il numero di telefono di un utente](assign-change-or-remove-a-phone-number-for-a-user.md).
    
## Vedere anche

#### 

[Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza](https://go.microsoft.com/fwlink/?LinkID=692099)
  
[Termini e condizioni per le chiamate al numero di emergenza](emergency-calling-terms-and-conditions.md)
  
[Periodo di chiamata in uscita di conferenze audio](../accessibility-and-regulatory/audio-conferencing-complimentary-dial-out-period.md)

