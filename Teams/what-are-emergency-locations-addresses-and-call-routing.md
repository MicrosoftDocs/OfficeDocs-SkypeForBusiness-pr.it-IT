---
title: Che cosa sono il routing delle chiamate, le posizioni e i luoghi di emergenza?
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
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.locations.emergencyaddresses.overview
- ms.lync.lac.AddressAndLocation
ms.custom:
- Calling Plans
description: 'Informazioni sulle posizioni di emergenza, sui luoghi e sul routing delle chiamate di emergenza e su come pianificarli e assegnarli agli utenti. '
ms.openlocfilehash: 4dbfe8d2a10c24ae66967030007328d2b9422e34
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "37925387"
---
# <a name="what-are-emergency-locations-places-and-call-routing"></a>Che cosa sono il routing delle chiamate, le posizioni e i luoghi di emergenza?

Quando si configurano i piani di chiamata, è necessario assegnare una posizione di emergenza a ogni numero di telefono quando si acquisisce il numero di telefono o quando lo si assegna a un utente per supportare le chiamate di emergenza. Prima di poter assegnare una posizione di emergenza a un numero di telefono, è necessario aggiungere e convalidare una posizione di emergenza. La convalida garantisce che la posizione di emergenza venga riconosciuta e che sia in un formato corretto che può essere usata dai servizi di risposta di emergenza. Se si vuole, è possibile aggiungere una posizione all'interno della posizione di emergenza per specificare un percorso più specifico per l'utente. Ad esempio, il luogo può essere un piano, un'ala o un ufficio collegato a una specifica posizione di emergenza. Anche se le posizioni di emergenza sono convalidate, i luoghi non sono.
  
## <a name="what-are-emergency-locations"></a>Che cosa sono le posizioni per gli interventi di emergenza?

È necessaria una posizione di emergenza per i numeri di telefono attivi e quando è necessario dipende dal paese/area geografica. Negli Stati Uniti è necessaria una posizione di emergenza quando un numero viene assegnato a un utente. Per altri paesi, ad esempio in Europa, Medio Oriente e Africa (EMEA), è necessaria una posizione di emergenza quando si riceve il numero di telefono da teams o quando viene trasferito da un altro provider di servizi o da un vettore a teams.
  
Un luogo di emergenza può essere indicato come indirizzo civico, indirizzo di strada o indirizzo fisico con la posizione facoltativa. È l'indirizzo civico o urbano di una sede aziendale per l'organizzazione. Ad esempio, l'indirizzo *12345 North Main Street, Redmond, WA 98052* viene usato per instradare le chiamate di emergenza alle autorità di spedizione appropriate e per facilitare l'individuazione del chiamante di emergenza. È probabile che sia necessario più di una posizione di emergenza se l'azienda ha più di un percorso aziendale fisico.
  
La convalida di un indirizzo di emergenza consiste nel verificare che sia legittimo e formattato correttamente per i servizi di emergenza. È possibile aggiungere e salvare una posizione di emergenza che non viene convalidata, ma solo i percorsi convalidati possono essere associati a un utente. Dopo aver convalidato e salvato un percorso di emergenza, è possibile assegnarlo a un utente. Per modificare un percorso di emergenza salvato e convalidato, sarà necessario crearne uno nuovo.
  
## <a name="what-are-places"></a>Cosa sono i luoghi?

Una posizione è associata a un luogo di emergenza per dare una posizione più esatta all'interno di un edificio. Una posizione è in genere un piano, un'ala di un edificio o un numero di ufficio in cui si trova l'utente. È possibile avere un numero illimitato di posizioni associate a un indirizzo di emergenza.
  
Quando si assegna una posizione di emergenza a un utente, si tratta in realtà di un ID posizione a cui si fa riferimento quando si assegna la posizione. L'ID posizione include l'indirizzo di emergenza a cui si fa riferimento (indirizzo civico o via). Una posizione predefinita è inclusa in un luogo di emergenza per i casi in cui le posizioni in costruzione non sono necessarie.
  
## <a name="what-is-emergency-call-routing"></a>Che cos'è il routing delle chiamate di emergenza?

Le posizioni e i luoghi di emergenza vengono usati durante il processo di routing delle chiamate di emergenza al centro di spedizione appropriato quando si inviano i primi risponditori di emergenza. Quando un utente di teams compone un numero di emergenza, in che modo la chiamata viene instradata al punto di PSAP (Public Safety Answering Point) che varia in base al paese e all'area geografica. In alcuni paesi, come gli Stati Uniti e il Regno Unito, le chiamate vengono prima visualizzate per determinare la posizione corrente dell'utente prima di connettere la chiamata al centro di distribuzione appropriato. In altri paesi e aree geografiche le chiamate vengono instradate direttamente al centro di distribuzione che serve il numero di telefono associato al chiamante di emergenza.
  
## <a name="create-add-and-assign-emergency-locations-and-places-to-your-users"></a>Creare, aggiungere e assegnare luoghi e posizioni di emergenza agli utenti

1. **Pianificare le posizioni di emergenza**. Il primo passaggio consiste nel pianificare le posizioni di emergenza. Elencare tutti gli indirizzi fisici. Quindi, in base a questo, determinare se sono necessarie posizioni per i percorsi di emergenza e, in caso affermativo, quali sono. Ad esempio, se un'azienda ha tre edifici di Office ognuno con quattro piani, è probabile che sia necessario disporre di tre posizioni di emergenza, con i piani da 1 a 4 elencati come posizione per ognuno.
    
2. **Aggiungere le posizioni di emergenza**. Il passaggio successivo consiste nell'aggiungere le posizioni di emergenza. Per altre informazioni, vedere [aggiungere, modificare o rimuovere una posizione di emergenza per l'organizzazione](add-change-remove-emergency-location-organization.md).
    
    > [!IMPORTANT]
    > La convalida di un indirizzo civico o stradale comporta la certezza che sia legittima e correttamente formattata. È possibile che un indirizzo di emergenza parzialmente corretto, ad esempio un nome digitato in modo errato della città, possa ancora superare la convalida. Il processo di convalida usa tutte le parti di un indirizzo specifico per determinare se contiene informazioni sufficienti per instradare la chiamata al centro di spedizione di emergenza appropriato. In caso affermativo, verrà restituito come convalidato e quindi può essere assegnato a un numero di telefono.
  
3. **Ottenere i numeri di telefono**. Il passaggio successivo consiste nell'ottenere i numeri di telefono per gli utenti. Puoi eseguire l'operazione ottenendo nuovi numeri di telefono da Office 365 o attraverso la "portabilità" o il trasferimento dei numeri di telefono esistenti in Office 365. Per visualizzare la procedura completa, vedere [trasferire i numeri di telefono in teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).
    
4. **Assegnare numeri di telefono**. L'ultimo passaggio consiste nel consentire agli utenti di effettuare e ricevere chiamate telefoniche. A questo scopo, devi assegnare un numero di telefono a ogni utente. Per assegnare un numero di telefono, vedere [assegnare, modificare o rimuovere il numero di telefono di un utente](/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user) .

> [!NOTE]
> Se è necessario ottenere più numeri di telefono, [contattare il servizio di assistenza PSTN](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md).

    
## <a name="related-topics"></a>Argomenti correlati

[Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Condizioni per le chiamate di emergenza](emergency-calling-terms-and-conditions.md)