---
title: Configurare gli account per Microsoft Teams Rooms
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: ''
description: Leggere questo argomento per informazioni sulla configurazione degli account per Microsoft Teams Rooms in Exchange e Skype for Business.
ms.openlocfilehash: 77e1dbe097bbb75697ec52ef7d472df4707ac9cb
ms.sourcegitcommit: 7eb66cb2955b17e89e1c162b6ca1b9bdb18189b2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2021
ms.locfileid: "61306121"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>Configurare gli account per Microsoft Teams Rooms
 
Leggere questo argomento per informazioni sulle Microsoft Teams Rooms e su come si integra con Exchange e Skype for Business.
  
Questo argomento illustra come creare account usati da Microsoft Teams Rooms in Microsoft Exchange e Skype for Business. È probabile che l'infrastruttura cada in una delle configurazioni seguenti:
  
- Distribuzione online: l'ambiente dell'organizzazione viene distribuito interamente in Microsoft 365 o Office 365. Per altre informazioni, vedere [Distribuire Microsoft Teams Rooms con Microsoft 365 o Office 365](with-office-365.md).
    
- Distribuzione locale: l'organizzazione ha server che controlla, in cui sono ospitati Active Directory, Exchange e Skype for Business Server. Per altre informazioni, vedere [Distribuire Microsoft Teams Rooms con Skype for Business Server](with-skype-for-business-server-2015.md)
    
- Distribuzioni ibride: l'organizzazione ha una combinazione di servizi, con alcuni ospitati in locale e altri online tramite Microsoft 365 o Office 365. Con Microsoft Teams Rooms, sono supportati gli scenari ibridi seguenti:
    
  - Exchange Online con Skype for Business Server locale. Per altre informazioni, vedere [Distribuire Microsoft Teams Rooms con Exchange Online (ibrida)](with-exchange-online.md).
    
  - Exchange locale con Microsoft Teams. Per altre informazioni, vedere [Distribuire Microsoft Teams Rooms con Exchange locale (ibrida).](with-exchange-on-premises.md)
    
La configurazione in uso influisce sulla modalità di preparazione per la configurazione del dispositivo.
  
Microsoft Teams Rooms deve essere assegnato un "account delle risorse" in Active Directory, Exchange e Skype for Business. L'account viene usato per accedere al calendario della riunione e stabilire Microsoft Teams o Skype for Business connettività. Gli utenti possono prenotare questo account pianificando una riunione con esso. Microsoft Teams Rooms potrà partecipare alla riunione e fornire varie funzionalità ai partecipanti alla riunione.
  
> [!IMPORTANT]
> Senza un account di risorsa, nessuna di queste caratteristiche funzionerà. 
  
Ogni account delle risorse è univoco per una singola Microsoft Teams Rooms e richiede alcune impostazioni:
  
- L'account della risorsa deve essere configurato correttamente.
    
- L'infrastruttura deve essere configurata per consentire Microsoft Teams Rooms convalidare l'account della risorsa e per raggiungere il servizi Microsoft.

> [!NOTE] 
> Se si usano Microsoft Teams, l'account della risorsa Teams Rooms accede sia ai Teams Rooms sia ai Teams associati.
    
> [!IMPORTANT]
> È consigliabile che la creazione dell'account sia eseguita con largo anticipo dell'installazione hardware effettiva. Idealmente, la preparazione dell'account viene avviata due o tre settimane prima dell'installazione.
> 

Negli ambienti ibridi l'account usato per Microsoft Teams Rooms deve avere la sincronizzazione delle password abilitata in Azure Active Directory (AAD) Sync perché l'autenticazione Microsoft Teams Rooms richiede Microsoft 365 o Office 365  autenticazione. Quando si configura l'account, assicurarsi che l'indirizzo SIP dell'account corrisponda al relativo nome dell'entità utente (UPN) in AAD. 
  
È possibile pensare a un account della risorsa come all'account della risorsa che gli utenti riconoscono come account di una sala riunioni o di uno spazio condiviso. Quando si vuole pianificare una riunione usando tale spazio, si invita l'account a quella riunione.
  
Se è già stato configurato un account della cassetta postale delle risorse per lo spazio in cui si sta installando Microsoft Teams Rooms, è possibile modificare l'account in un account Teams Rooms risorsa. Al termine, tutto quello che devi fare è accedere a Microsoft Teams Rooms con quell'account.
  
## <a name="basic-configuration"></a>Configurazione di base

Queste proprietà rappresentano la configurazione minima per l'utilizzo di un account delle risorse con Microsoft Teams Rooms. L'account della risorsa potrebbe richiedere un'ulteriore configurazione.
  
|**Proprietà**|**Scopo**|
|:-----|:-----|
|Exchange cassetta postale (Exchange 2013 SP1 o versione successiva o Exchange Online)  <br/> |L'abilitazione dell'account con una cassetta postale di Exchange offre all'account della risorsa la possibilità di ricevere e inviare sia messaggi di posta elettronica che convocazioni di riunione e di visualizzare un calendario delle riunioni nel Microsoft Teams Rooms dispositivo. La Microsoft Teams Rooms cassetta postale deve essere una cassetta postale della chat room.  <br/> |
|Skype for Business è abilitato  <br/> |Skype for Business può essere abilitato per usare varie funzionalità di conferenza Skype for Business, come videochiamate, messaggistica istantanea e condivisione dello schermo.  <br/> |
|Password abilitata  <br/> |L'account della risorsa deve essere abilitato con una password o non può eseguire l'autenticazione con Microsoft Teams, Exchange o Skype for Business Server. La scadenza della password deve essere disabilitata in Teams Rooms account delle risorse.   <br/> |
   
## <a name="advanced-configuration"></a>Configurazione avanzata

Anche se le proprietà per la configurazione di base consentono di configurare l'account della risorsa in un ambiente semplice, è possibile che l'ambiente abbia altre restrizioni sugli account della directory che devono essere rispettate per consentire a Microsoft Teams Rooms di usare correttamente l'account delle risorse.
  
|**Proprietà**|**Scopo**|
|:-----|:-----|
|Autenticazione basata su certificati  <br/> |I certificati possono essere necessari sia per Exchange che per Skype for Business Server. Per distribuire i certificati, è possibile caricarli quando si è connessi come amministratore.  <br/> |
  
## <a name="see-also"></a>Vedere anche

[Piano per Microsoft Teams Rooms](rooms-plan.md)
  
[Configurare una console per Microsoft Teams Rooms](console.md)
  
[Gestire Microsoft Teams Rooms](rooms-manage.md).
