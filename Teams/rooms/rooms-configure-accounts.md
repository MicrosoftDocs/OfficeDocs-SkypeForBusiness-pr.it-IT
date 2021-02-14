---
title: Configurare gli account per le sale di Microsoft Teams
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: ''
description: Leggere questo argomento per informazioni sulla configurazione degli account per le sale di Microsoft Teams in Exchange e Skype for Business.
ms.openlocfilehash: e171ef22dd1733c06b03a4a9483f591d73d70cb9
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662521"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>Configurare gli account per le sale di Microsoft Teams
 
Leggere questo argomento per informazioni sulle sale di Microsoft Teams e su come si integra con Exchange e Skype for Business.
  
Questo argomento illustra come creare account usati da Microsoft Teams Rooms in Microsoft Exchange e Skype for Business. Le istruzioni per la distribuzione per i dispositivi di Microsoft Teams Rooms sono fornite in [Configurare una console di Microsoft Teams Rooms.](console.md) È probabile che l'infrastruttura sia in una delle configurazioni seguenti:
  
- Distribuzione online: l'ambiente dell'organizzazione viene distribuito interamente in Microsoft 365 o Office 365. Per altre informazioni, vedere [Distribuire sale di Microsoft Teams con Microsoft 365 o Office 365.](with-office-365.md)
    
- Distribuzione locale: la tua organizzazione dispone di server che controlla, dove sono ospitati Active Directory, Exchange e Skype for Business Server. Per altre informazioni, vedere [Distribuire sale di Microsoft Teams con Skype for Business Server](with-skype-for-business-server-2015.md)
    
- Distribuzioni ibride: l'organizzazione ha una combinazione di servizi, alcuni ospitati in locale e altri online tramite Microsoft 365 o Office 365. Con Le sale di Microsoft Teams sono supportati i seguenti scenari ibridi:
    
  - Exchange Online con Skype for Business Server locale. Per altre informazioni, vedere [Distribuire sale di Microsoft Teams con Exchange Online (ibrido).](with-exchange-online.md)
    
  - Exchange locale con Microsoft Teams o Skype for Business online. Per altre informazioni, vedere [Distribuire sale di Microsoft Teams con Exchange locale (ibrido).](with-exchange-on-premises.md)
    
La configurazione di cui si dispone influisce sulla modalità di preparazione per la configurazione del dispositivo.
  
Alle sale di Microsoft Teams deve essere assegnato un "account dispositivo" in Active Directory, Exchange e Skype for Business. L'account viene usato per accedere al calendario della riunione e stabilire la connettività di Microsoft Teams o Skype for Business. Gli utenti possono prenotare questo account pianificando una riunione. Le sale di Microsoft Teams potranno partecipare alla riunione e fornire varie funzionalità ai partecipanti alla riunione.
  
> [!IMPORTANT]
> Senza un account del dispositivo, nessuna di queste funzionalità funzionerà. 
  
Ogni account del dispositivo è univoco per un singolo dispositivo Microsoft Teams Rooms e richiede alcune configurazioni:
  
- L'account del dispositivo deve essere configurato correttamente.
    
- L'infrastruttura deve essere configurata per consentire a Microsoft Teams Room di convalidare l'account del dispositivo e raggiungere i servizi Microsoft appropriati.
    
> [!IMPORTANT]
> È consigliabile eseguire la creazione dell'account con largo anticipo dell'installazione hardware effettiva. Idealmente, la preparazione dell'account viene avviata due-tre settimane prima dell'installazione. 

Negli ambienti ibridi l'account usato per le sale di Microsoft Teams deve avere la sincronizzazione delle password abilitata nella sincronizzazione di Azure Active Directory (AAD) perché l'autenticazione delle sale di Microsoft Teams richiede l'autenticazione di Microsoft 365 o Office 365. Quando si configura l'account, assicurarsi che l'indirizzo SIP dell'account corrisponda al relativo nome dell'entità utente (UPN) in AAD. 
  
Si può pensare a un account del dispositivo come all'account delle risorse che le persone riconoscono come account della sala riunioni o dell'area riunioni. Se si vuole pianificare una riunione tramite tale sala riunioni, si invita l'account a tale riunione. Per usare al meglio le sale di Microsoft Teams, è necessario eseguire la stessa operazione con l'account del dispositivo assegnato a ognuna di queste.
  
Se è già stato configurato un account della cassetta postale delle risorse per l'area riunioni in cui si installa Microsoft Teams Rooms, è possibile modificare l'account della risorsa in un account del dispositivo. Al termine, è necessario aggiungere l'account del dispositivo a un dispositivo Microsoft Teams Rooms. Vedere gli esempi di configurazione dell'account del dispositivo forniti di seguito.
  
Con una configurazione aggiuntiva, la gestione remota è possibile usare Microsoft Azure Monitor come descritto in Pianificare la gestione delle sale di Microsoft Teams con [Il monitor Di Azure,](azure-monitor-plan.md)distribuire la gestione delle sale di Microsoft Teams con Il monitor [di Azure](azure-monitor-deploy.md)e gestire i dispositivi delle sale di Microsoft Teams con Il monitor [di Azure.](azure-monitor-manage.md) 
  
## <a name="basic-configuration"></a>Configurazione di base

Queste proprietà rappresentano la configurazione minima per l'uso di sale di Microsoft Teams per un account dispositivo. L'account del dispositivo potrebbe richiedere ulteriori configurazioni.
  
|**Proprietà**|**Scopo**|
|:-----|:-----|
|Cassetta postale di Exchange (Exchange 2013 SP1 o versioni successive o Exchange Online)  <br/> |L'abilitazione dell'account con una cassetta postale di Exchange offre all'account del dispositivo la possibilità di ricevere e inviare convocazioni di riunione e di posta elettronica e di visualizzare un calendario delle riunioni nel dispositivo Microsoft Teams Rooms. La cassetta postale Sale di Microsoft Teams deve essere una cassetta postale della sala.  <br/> |
|Skype for Business è abilitato  <br/> |Skype for Business deve essere abilitato per poter usare varie funzionalità di conferenza, come videochiamate, messaggistica istantanea e condivisione dello schermo. Sono supportati sia Skype for Business online che Skype for Business Server.  <br/> |
|Password abilitata  <br/> |L'account del dispositivo deve essere abilitato con una password o non può eseguire l'autenticazione con Exchange o Skype for Business Server.  <br/> |
   
## <a name="advanced-configuration"></a>Configurazione avanzata

Anche se le proprietà della configurazione di base consentono di configurare l'account del dispositivo in un ambiente semplice, è possibile che l'ambiente abbia altre restrizioni sugli account della directory che devono essere soddisfatte per consentire a Microsoft Teams Room di usare correttamente l'account del dispositivo.
  
|**Proprietà**|**Scopo**|
|:-----|:-----|
|Autenticazione basata su certificato  <br/> |Potrebbero essere necessari certificati sia per Exchange che per Skype for Business Server. Per distribuire i certificati, è possibile caricarli quando si è connessi come amministratore.  <br/> |
   
Il modo più semplice per configurare gli account dei dispositivi è configurarli usando le Windows PowerShell. Microsoft fornisce [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), uno script che consente di creare nuovi account del dispositivo o convalidare gli account delle risorse esistenti in uso per poterli convertire in account compatibili per dispositivi Microsoft Teams Rooms.
  
Se si preferisce usare l'interfaccia utente di Microsoft 365 o Office 365 invece dei cmdlet Windows PowerShell, alcuni passaggi possono essere eseguiti manualmente. Vedere [Creazione di un account per dispositivi con Microsoft 365 o Office 365.](https://docs.microsoft.com/surface-hub/create-a-device-account-using-office-365)
  
## <a name="see-also"></a>Vedere anche

[Piano per Microsoft Teams Rooms](rooms-plan.md)
  
[Configurare una console per Microsoft Teams Rooms](console.md)
  
[Gestire Microsoft Teams Rooms](rooms-manage.md).

