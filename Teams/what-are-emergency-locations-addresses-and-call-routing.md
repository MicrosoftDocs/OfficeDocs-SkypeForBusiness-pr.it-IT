---
title: Quali sono le posizioni di emergenza, gli indirizzi e il routing delle chiamate?
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.locations.emergencyaddresses.overview
- ms.lync.lac.AddressAndLocation
ms.custom:
- Calling Plans
description: 'Learn what emergency address, location, and emergency call routing are, and how to plan and assign them to your users. '
ms.openlocfilehash: 979fab1cd099d568278efd61d06a3f8a75b04541
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "36483865"
---
# <a name="what-are-emergency-locations-addresses-and-call-routing"></a>Quali sono le posizioni di emergenza, gli indirizzi e il routing delle chiamate?

Quando si configurano i piani per le chiamate in Office 365, è necessario assegnare un indirizzo di emergenza a ogni numero di telefono quando si ottiene il numero di telefono o lo si assegna a un utente per supportare le chiamate di emergenza. Prima di poter assegnare un indirizzo di emergenza a un numero di telefono, è necessario creare e convalidare l'indirizzo di emergenza. La convalida garantisce che l'indirizzo di emergenza sia riconosciuto e che sia in un formato corretto che può essere usato dai servizi di risposta di emergenza. Facoltativamente, è possibile aggiungere una posizione all'interno dell'indirizzo di emergenza per specificare un percorso più specifico per l'utente. Ad esempio, la posizione di emergenza può essere un piano, un'ala o un ufficio collegato a un indirizzo di emergenza specifico. Anche se l'indirizzo di emergenza viene convalidato, le posizioni non sono.
  
## <a name="what-are-emergency-addresses"></a>Che cosa sono gli indirizzi per gli interventi di emergenza?

È necessario un indirizzo di emergenza per i numeri di telefono attivi, ma quando è necessario dipende dal paese/area geografica. Negli Stati Uniti è necessario un indirizzo di emergenza quando un numero viene assegnato a un utente. Per altri paesi, ad esempio in Europa, Medio Oriente e Africa (EMEA), è necessario un indirizzo di emergenza quando si riceve il numero di telefono da Office 365 o quando viene trasferito da un altro provider o gestore di servizi.
  
Un indirizzo di emergenza può essere indicato come indirizzo civico, indirizzo stradale o indirizzo fisico. Si tratta dell'indirizzo stradale o dell'indirizzo civico di un luogo di lavoro per l'organizzazione. Ad esempio, l'indirizzo *12345 North Main Street, Redmond, WA 98052* viene usato per instradare le chiamate di emergenza alle autorità di spedizione appropriate e per facilitare l'individuazione del chiamante di emergenza. Se la tua azienda ha più di una posizione fisica potresti dover fornire più di un indirizzo per gli interventi di emergenza.
  
Per la convalida di un indirizzo di emergenza, è necessario assicurarsi che sia legittimo e formattato correttamente per i servizi di risposta di emergenza. È possibile creare e salvare un indirizzo di emergenza non convalidato, ma solo gli indirizzi convalidati possono essere associati a un utente. Un indirizzo per gli interventi di emergenza deve essere convalidato e salvato prima di poter essere associato a un utente. Se è necessario apportare una modifica a un indirizzo per gli interventi di emergenza convalidato, è necessario crearne uno nuovo.
  
## <a name="what-are-emergency-locations"></a>Che cosa sono le posizioni per gli interventi di emergenza?

Una posizione di emergenza è associata a un indirizzo di emergenza per ottenere una posizione più esatta all'interno di un edificio. La posizione per gli interventi di emergenza può corrispondere di solito al piano, all'ala dell'edificio o al numero dell'ufficio in cui si trova l'utente. È possibile avere un numero illimitato di posizioni associate a un indirizzo di emergenza. 
  
Quando si assegna un indirizzo di emergenza a un utente, si tratta in realtà di un ID posizione a cui viene fatto riferimento quando si assegna l'indirizzo. L'ID posizione include l'indirizzo di emergenza a cui si fa riferimento (indirizzo civico o via). Una posizione di emergenza predefinita è inclusa in un indirizzo di emergenza per i casi in cui non sono necessarie posizioni in costruzione. 
  
## <a name="what-is-emergency-call-routing"></a>Che cos'è il routing delle chiamate di emergenza?

Gli indirizzi e le posizioni di emergenza vengono usati durante il processo di routing delle chiamate di emergenza al centro di spedizione appropriato quando si inviano i primi risponditori di emergenza. Quando un utente di teams o Skype for business compone un numero di emergenza, il modo in cui viene instradata la chiamata al punto di PSAP (Public Safety Answering Point) che varia in base al paese o all'area geografica. In alcuni paesi, come gli Stati Uniti e il Regno Unito, le chiamate verranno dapprima visualizzate per determinare la posizione corrente dell'utente prima di connettere la chiamata al centro di distribuzione appropriato. In altri paesi/aree geografiche le chiamate verranno instradate direttamente al centro di distribuzione che serve il numero di telefono associato al chiamante di emergenza.
  
## <a name="create-add-and-assign-emergency-locations-and-addresses-to-your-users"></a>Creare, aggiungere e assegnare indirizzi e posizioni di emergenza agli utenti

1. **Pianificare le posizioni di emergenza**. Il primo passaggio consiste nel pianificare le posizioni di emergenza. Devi elencare tutti gli indirizzi fisici. Quindi, in base a questo, determinare se sono necessarie posizioni per gli indirizzi di emergenza e, in caso affermativo, quali sono. Ad esempio, se un'azienda ha 3 edifici per uffici ognuno con 4 piani, è probabile che sia necessario disporre di 3 indirizzi di emergenza, con piani 1-4 elencati come posizione per ciascuno di essi.
    
2. **Creare e convalidare le posizioni di emergenza**. Il passaggio successivo consiste nel creare e convalidare gli indirizzi di emergenza. Quando crei un indirizzo per gli interventi di emergenza, puoi convalidarlo. Per creare un indirizzo di emergenza, vedere [aggiungere o rimuovere un indirizzo di emergenza per l'organizzazione](/SkypeForBusiness/what-are-calling-plans-in-office-365/add-or-remove-an-emergency-address-for-your-organization).
    
    > [!IMPORTANT]
    > La convalida di un indirizzo civico o stradale implica la verifica della legittimità e della corretta formattazione dell'indirizzo. È possibile che un indirizzo di emergenza parzialmente corretto, ad esempio un nome digitato in modo errato della città, possa ancora superare la convalida. Il processo di convalida utilizza tutte le parti di un dato indirizzo per stabilire se contiene informazioni sufficienti a inoltrare la chiamata al centro dei servizi di emergenza più appropriato. In caso affermativo, verrà restituito come convalidato e quindi può essere assegnato a un numero di telefono. 
  
3. **Ottenere i numeri di telefono**. Il passaggio successivo consiste nell'ottenere i numeri di telefono per gli utenti. Puoi eseguire l'operazione ottenendo nuovi numeri di telefono da Office 365 o attraverso la "portabilità" o il trasferimento dei numeri di telefono esistenti in Office 365. Per visualizzare la procedura completa, vedere [trasferire i numeri di telefono in Office 365](transfer-phone-numbers-to-office-365.md).
    
4. **Assegnare numeri di telefono**. L'ultimo passaggio consiste nel consentire agli utenti di effettuare e ricevere chiamate telefoniche. A questo scopo, devi assegnare un numero di telefono a ogni utente. Per assegnare un numero di telefono, vedere [assegnare, modificare o rimuovere il numero di telefono di un utente](/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user) .

> [!NOTE]
> Se hai bisogno di ulteriori numeri di telefono, visita la pagina [Contattare il supporto per i prodotti aziendali - Guida per gli amministratori](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

    
## <a name="related-topics"></a>Argomenti correlati
[Cos'è la convalida dell'indirizzo?](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Termini e condizioni per le chiamate al numero di emergenza](emergency-calling-terms-and-conditions.md)

[Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

