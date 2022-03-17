---
title: Configurare gli account per Microsoft Teams Rooms
ms.author: czawideh
author: cazawideh
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
description: Leggere questo argomento per informazioni sulla configurazione di account per Microsoft Teams Rooms (inclusi Surface Hub) e telefoni dell'area comune.
ms.openlocfilehash: 4ecac71ef862fda003523bbcefe3c333daefaa23
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/16/2022
ms.locfileid: "63514731"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>Configurare gli account per Microsoft Teams Rooms
 
Questo argomento illustra come creare account usati da Microsoft Teams Rooms. È probabile che l'infrastruttura cada in una delle configurazioni seguenti:
  
- Distribuzione online: l'ambiente dell'organizzazione viene distribuito interamente in Microsoft 365 o Office 365.
    
- Distribuzione locale: l'organizzazione ha server che controlla, in cui sono ospitati Active Directory, Exchange e Skype for Business Server. Per altre informazioni, vedere [Distribuire Microsoft Teams Rooms con Skype for Business Server](with-skype-for-business-server-2015.md)
    
- Distribuzioni ibride: l'organizzazione ha una combinazione di servizi, con alcuni ospitati in locale e altri online tramite Microsoft 365 o Office 365. Con Microsoft Teams Rooms, sono supportati gli scenari ibridi seguenti:
    
  - Exchange Online con Skype for Business Server locale.
    
  - Exchange locale con Microsoft Teams.
    
La configurazione in uso influisce sulla modalità di preparazione per la configurazione del dispositivo.
  
Microsoft Teams Rooms avere un "account delle risorse" in Active Directory, Exchange e (se necessario) Skype for Business. L'account viene usato per accedere al calendario della riunione e stabilire Microsoft Teams e/o Skype for Business connettività. Gli utenti possono prenotare questo account pianificando una riunione con esso. Microsoft Teams Rooms potrà partecipare alla riunione e fornire varie funzionalità ai partecipanti alla riunione.
  
> [!IMPORTANT]
> Senza un account di risorsa, nessuna di queste caratteristiche funzionerà.
  
Ogni account delle risorse è univoco per una singola Microsoft Teams Rooms installazione.
  
- L'account della risorsa deve essere configurato correttamente.
    
- L'infrastruttura deve essere configurata per consentire Microsoft Teams Rooms convalidare l'account della risorsa e raggiungere l'account servizi Microsoft.

> [!NOTE] 
> Se si usano Microsoft Teams, l'account della risorsa Teams Rooms accede sia ai Teams Rooms che ai Teams associati.
    
> [!IMPORTANT]
> È consigliabile che la creazione dell'account sia eseguita con largo anticipo dell'installazione hardware effettiva. Idealmente, la preparazione dell'account viene avviata due o tre settimane prima dell'installazione.
> 
Negli ambienti ibridi che non usano Skype for Business, è consigliabile creare l'account in modo nativo in Azure Active Directory. Se l'account deve essere creato con Active Directory locale, la sincronizzazione delle password deve essere abilitata nella sincronizzazione di Azure Active Directory (AAD) Connessione perché l'autenticazione Microsoft Teams Rooms richiede Microsoft 365 o Office 365  autenticazione. Quando si configura l'account, assicurarsi che l'indirizzo di posta elettronica dell'account corrisponda al relativo nome dell'entità utente (UPN) in AAD. 
  
Un account delle risorse può essere pensato come l'account che gli utenti riconoscono come il nome di una sala riunioni o di uno spazio condiviso. Quando si vuole pianificare una riunione usando tale spazio, si invita l'account della risorsa a quella riunione.
  
Se è già stato configurato un account della cassetta postale della risorsa Exchange per lo spazio in cui si sta installando Microsoft Teams Rooms, è possibile modificare l'account in un account Teams Rooms risorsa. Al termine, tutto quello che devi fare è accedere a Microsoft Teams Rooms con quell'account.
  
## <a name="basic-configuration"></a>Configurazione di base

Queste proprietà rappresentano la configurazione minima per l'utilizzo di un account delle risorse con Microsoft Teams Rooms. L'account della risorsa potrebbe richiedere un'ulteriore configurazione.
  
|**Proprietà**|**Scopo**|
|:-----|:-----|
|Exchange cassetta postale (Exchange 2013 SP1 o versione successiva o Exchange Online)  <br/> |La Exchange cassetta postale offre all'account della risorsa la possibilità di ricevere e inviare posta e convocazioni di riunione e di visualizzare un calendario delle riunioni Microsoft Teams Rooms. La Microsoft Teams Rooms cassetta postale deve essere una cassetta postale della risorsa di tipo "room".  <br/> |
|Skype for Business è abilitato  <br/> |Skype for Business può essere abilitato per usare varie funzionalità di conferenza Skype for Business, ad esempio videochiamate, messaggistica istantanea e condivisione dello schermo.  <br/> |
|Password abilitata  <br/> |L'account della risorsa deve essere abilitato con una password o non può eseguire l'autenticazione con Microsoft Teams, Exchange o Skype for Business Server. La scadenza della password deve essere disabilitata in Teams Rooms account delle risorse.   <br/> |
   
## <a name="advanced-configuration"></a>Configurazione avanzata

Anche se le proprietà per la configurazione di base consentono di configurare l'account delle risorse in un ambiente semplice, è possibile che l'ambiente abbia altre restrizioni sugli account che devono essere rispettate per consentire a Microsoft Teams Rooms di usare correttamente l'account delle risorse.
  
|**Proprietà**|**Scopo**|
|:-----|:-----|
|Autenticazione basata su certificati  <br/> |Potrebbero essere necessari certificati sia per Exchange che per Skype for Business Server. Per distribuire i certificati, è possibile caricarli quando si è connessi come amministratore.  <br/> |

## <a name="see-also"></a>Vedere anche

[Piano per Microsoft Teams Rooms](rooms-plan.md)
  
[Configurare una console per Microsoft Teams Rooms](console.md)
  
[Gestire Microsoft Teams Rooms](rooms-manage.md).
