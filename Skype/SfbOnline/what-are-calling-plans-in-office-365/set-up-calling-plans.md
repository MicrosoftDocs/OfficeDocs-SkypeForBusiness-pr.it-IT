---
title: Configurare le chiamate PSTN per Skype for Business
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 57893158-1acd-44ac-acaf-19f58264a9e0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
- LIL_Placement
description: 'Learn how in Office 365 Calling Plan (PSTN Calling plan) to buy and set up licenses, get phone numbers, add and assign emergency locations and phone numbers to users, and tell your users about their new phone numbers. '
ms.openlocfilehash: 871edfa997e9267213480a448eda952a7927783b
ms.sourcegitcommit: 6c59400d2e677c1022f320c91cd7f102b99d292b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/08/2018
---
# <a name="set-up-calling-plans"></a>Configurare le chiamate PSTN per Skype for Business

Calls to other Skype for Business users are free, but if you want your users to be able to call phones outside of your business, get a Domestic Calling Plan or an International Calling Plan in Office 365. It's easy to set this up for your business. 
  
## <a name="step-1-buy-and-assign-licenses"></a>Passaggio 1: acquisto e assegnazione delle licenze

1. If the Phone System in Office 365 feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses. Dopo avere licenze **Sistema telefonico** , acquistare [La chiamata dei piani di Office 365](../skype-for-business-and-microsoft-teams-add-on-licensing/calling-plans-for-office-365.md). See [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md), and buy the licenses and plan. 
    
    > [!TIP]
    > Le licenze Cloud PBX e i piani per chiamate vocali vanno di pari passo, perciò per vedere l'opzione per acquistare un piano di chiamate vocali devi prima comprare le licenze Cloud PBX.
  
2. First assign the licenses, and then assign a Calling Plan to the people in your organization. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).
    
## <a name="step-2-get-phone-numbers"></a>Passaggio 2: ottenere i numeri di telefono

Se l'azienda non è negli Stati Uniti, l'ordine dei passaggi è leggermente diverso. Questo perché in alcuni paesi/aree geografiche riceverai un indirizzo per gli interventi di emergenza insieme al numero di telefono ricevuto da Office 365 o al numero di telefono trasferito. Perciò, se non sei negli Stati Uniti, procedi prima con il [Passaggio 3: aggiungere posizioni e indirizzi per gli interventi di emergenza per l'organizzazione.](set-up-calling-plans.md#bkmk_add_addresses), e poi con il **Passaggio 2:ottenere i numeri di telefono**.
  
1. Se utilizzi numeri di telefono di Office 365, puoi seguire questa procedura. **Se è necessario trasferire numeri di telefono esistenti da un altro provider di servizi o gestore, dovrai eseguire la procedura descritta nell'argomento [Trasferire numeri di telefono in Skype for Business online](transfer-phone-numbers-to-office-365.md)**.
    
2. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
3. Passa all' **interfaccia di amministrazione di Office 365** > **Interfacce amministratore** > **Skype for Business >** **Voce**.

    > [!IMPORTANT] 
    > Per poter visualizzare l'opzione **vocale** nel riquadro di spostamento sinistra in Skype per interfaccia di amministrazione di Business, è necessario acquistare una licenza di componente aggiuntivo **Per conferenze Audio** , una licenza di componente aggiuntivo di **Sistema telefonico** o almeno una **licenza Enterprise E5**.
   
4. Choose **Phone numbers**. You'll see how many **Phone System** licenses you have, to give you an idea how many phone numbers to request.
    
    > [!TIP]
    > Puoi acquisire più numeri di telefono che licenze disponibili. Per determinare quanti numeri di telefono puoi acquisire, aggiungi il 10% delle tue licenze e poi aggiungi 10. Ad esempio, se hai acquistato 100 licenze, puoi acquisire 120 numeri di telefono. Vedere [quanti numeri trovare?](how-many-phone-numbers-can-you-get.md) 
  
5. Choose **Add new number** > **New user numbers**, and on the **Add new user numbers** page, choose the country/region, state/region, and city that you want to select numbers from.
    
6.  In **Quantità**, inserisci quanti numeri di telefono vuoi impostare da quest'area per l'organizzazione e quindi fai clic su **Aggiungi** per creare una prenotazione.
    
    > [!CAUTION]
    > Hai 10 minuti di tempo per selezionare i numeri di telefono. Se superi i 10 minuti, i numeri di telefono verranno restituiti nel pool di numeri in Office 365. 
  
    Nell'immagine seguente, come puoi vedere, ho aggiunto i numeri di telefono per due città diverse e ho 9 minuti rimasti per acquisirli. 
    
     ![At the Add user numbers page, specify the area where you want to get the numbers for.](../images/f6dc1ef3-0bf2-4b4f-b32c-ca27e69c5553.png)
  
7. Seleziona **Mostra numeri** per visualizzare l'elenco completo dei numeri di telefono. Questa funzionalità è utile se non desideri selezionare un numero di telefono incluso nell'elenco.
    
8. Seleziona i numeri di telefono desiderati e quindi seleziona **Acquisisci numeri**.
    
9. Tornerai alla pagina Voce, dove sono elencati tutti i numeri di telefono acquisiti.
    
    ![At the Voice dashboard, you'll see all the phone numbers you acquired.](../images/4a9c681c-13f9-4cdc-a25b-93eb00d06b6c.png)
  
## <a name="step-3-add-emergency-addresses-and-locations-for-your-organization"></a>Passaggio 3: aggiungere posizioni e indirizzi per gli interventi di emergenza per l'organizzazione.
<a name="bkmk_add_addresses"> </a>

1. Nella pagina **Voce**, seleziona **Posizione per gli interventi di emergenza** > **Aggiungi**.
    
2. Nel riquadro **Nuovo indirizzo**, immetti un nome per l'indirizzo e poi compila le caselle restanti.
    
     ![When you enter a new emergency address, the formatting of the street name might cause an error.](../images/dc1c5ef3-0554-4fb7-9ab1-5ea3ac9e5eb5.png)
  
    > [!TIP]
    > Per i clienti di lingua inglese, se il nome della strada è un numero, assicurarsi di includere la desinenza (come "st" o "th") come indicato nella figura sopra. 
  
3. Seleziona **Convalida**.
    
    Se necessario, ti sarà chiesto di fare correzioni all'indirizzo. 
    
    > [!CAUTION]
    > La convalida di un indirizzo civico o stradale implica la verifica della legittimità e della corretta formattazione dell'indirizzo. È possibile che un indirizzo per gli interventi di emergenza parzialmente corretto, in cui hai ad esempio digitato erroneamente il nome della città, superi comunque la fase di convalida. In caso di convalida nonostante gli errori di ortografia, la combinazione del nome della città errato e delle altre parti corrette dell'indirizzo fornisce informazioni sufficienti per instradare la chiamata al centro di emergenza appropriato. 
  
    > [!TIP]
    > Se l'indirizzo deve essere corretto per un intervento di emergenza, verrà visualizzato un banner verde per indicare che l'indirizzo è stato aggiornato. 
  
4. Dopo la convalida dell'indirizzo, seleziona **Salva**.
    
## <a name="step-4-assign-phone-numbers-and-emergency-addresses-to-users"></a>Passaggio 4: assegnare numeri di telefono e indirizzi di emergenza agli utenti
<a name="bkmk_add_addresses"> </a>

> [!TIP]
> Se aggiungi altre persone alla tua azienda appena prima di questo passaggio, possono passare **diverse ore** prima che compaiano nella pagina **Utenti vocali**. C'è un periodo di latenza.
  
1. Nella pagina **Utenti vocali**, scegli le persone a cui vuoi assegnare un numero di telefono e un indirizzo per gli interventi di emergenza.
    
2. Seleziona **Assegna numero**.
    
3. Nella pagina **Assegna numero**, nel menu a discesa **Seleziona il numero da assegnare** scegli il numero di telefono per l'utente.
    
4. Per selezionare un indirizzo per gli interventi di emergenza, inserisci il nome della città nella casella **Trova città** e seleziona Cerca.
    
    > [!IMPORTANT]
    > Se non ti trovi negli Stati Uniti, i tuoi numeri hanno già un indirizzo per gli interventi di emergenza, ma puoi modificarlo in questa fase. Consulta [Assegnare o modificare l'indirizzo per gli interventi di emergenza di un utente](assign-or-change-an-emergency-address-for-a-user.md). 
  
5. Dopo avere assegnato sia il numero di telefono sia l'indirizzo per gli interventi di emergenza, seleziona **Salva**.
    
## <a name="step-5-tell-your-users-about-their-new-phone-numbers"></a>Passaggio 5: comunicare agli utenti il nuovo numero di telefono
<a name="bkmk_add_addresses"> </a>

Consigliamo di inviare e-mail o usare il metodo di comunicazione standard dell'azienda per comunicare alle persone il nuovo numero di telefono. 

Ecco come è possibile visualizzare tale numero di telefono nel proprio app **Skype for Business** :
  
1. Esegui l'accesso a Skype for Business sul desktop.
    
2. Seleziona **Impostazioni** > **Strumenti** > **Opzioni**. 
    
     ![To view your phone number, go to Settings > Tools > Options.](../images/20637117-91d7-4a7e-9f06-7abc634a9211.png)
  
3. Poi seleziona **Telefoni**. 
    
    ![A user can see their assign number in the Skype for Business app by choosing Settings > Tools > Options > Phone.](../images/0128d667-2bf8-4165-b703-e9b78a15b63c.png)
 
In **Team Microsoft che**gli utenti possono visualizzare il numero di telefono fare clic sulle **chiamate** nel riquadro di spostamento sinistro. Il numero di telefono viene visualizzato sopra la tastiera.

![Un utente può visualizzare il numero di Microsoft Teams facendo clic sulle chiamate nel riquadro di spostamento sinistro.](../images/teams-phone-number.png)

## <a name="what-else-do-you-need-to-know"></a>Per saperne di più
<a name="bkmk_add_addresses"> </a>

- Spesso per indirizzo per gli interventi di emergenza si può intendere un indirizzo civico, un indirizzo stradale o un indirizzo fisico. Si tratta dell'indirizzo stradale o dell'indirizzo civico di un luogo di lavoro per l'organizzazione.
    
- Solo gli indirizzi per gli interventi di emergenza sono convalidati, non le posizioni.
    
- Se desideri consultare ulteriori informazioni sugli indirizzi di emergenza, vedi [Che cosa sono il routing delle chiamate, gli indirizzi e le posizioni per gli interventi di emergenza?](what-are-emergency-locations-addresses-and-call-routing.md)
    
## <a name="do-you-want-to-automate-assigning-phone-numbers"></a>Vuoi automatizzare l'assegnazione dei numeri di telefono?
<a name="bkmk_add_addresses"> </a>

Se conosci Windows PowerShell, puoi usare questi cmdlet per automatizzare l'assegnazione dei numeri di telefono ai tuoi utenti. 
  
- [Get-CsOnlineTelephoneNumber](https://technet.microsoft.com/en-us/library/mt243818.aspx): Recupera i numeri di telefono dal tuo elenco vocale aziendale.
    
- [Set-CsOnlineVoiceUser](https://technet.microsoft.com/en-us/library/mt243817.aspx): Imposta i numeri di telefono.
    
Per maggiori informazioni, consulta [Riferimento rapido:Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362776%28v=ocs.15%29.aspx).
  
    > [!NOTE]
    > If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/en-us/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a>Argomenti correlati
[Domande comuni sul trasferimento dei numeri di telefono](transferring-phone-numbers-common-questions.md)

[Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gestire i numeri di telefono per la propria organizzazione](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Termini e condizioni per le chiamate al numero di emergenza](emergency-calling-terms-and-conditions.md)

[Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza](https://go.microsoft.com/fwlink/?LinkID=692099)

## <a name="feedback"></a>Commenti e suggerimenti?
Per inviare commenti e suggerimenti prodotto o per consentire us sapere come ci si limita, vedere [Skype per commenti e suggerimenti Business](https://www.skypefeedback.com).