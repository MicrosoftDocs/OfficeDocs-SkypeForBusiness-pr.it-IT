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
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: ''
description: Leggere questo argomento per informazioni sulla configurazione degli account per Microsoft Teams Rooms in Exchange e Skype for Business.
ms.openlocfilehash: 26879b2c07b859e65255ed84bedd4897b75d5caa
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117474"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>Configurare gli account per Microsoft Teams Rooms
 
Leggere questo argomento per informazioni su Microsoft Teams Rooms e su come si integra con Exchange e Skype for Business.
  
Questo argomento illustra come creare account usati da Microsoft Teams Rooms in Microsoft Exchange e Skype for Business. Le istruzioni per la distribuzione per i dispositivi Microsoft Teams Rooms sono trattate in [Configurare una console di Microsoft Teams Rooms.](console.md) È probabile che l'infrastruttura cada in una delle configurazioni seguenti:
  
- Distribuzione online: l'ambiente dell'organizzazione è distribuito interamente in Microsoft 365 o Office 365. Per altre informazioni, vedere [Distribuire le chat room di Microsoft Teams con Microsoft 365 o Office 365.](with-office-365.md)
    
- Distribuzione locale: l'organizzazione ha server che controlla, in cui sono ospitati Active Directory, Exchange e Skype for Business Server. Per altre informazioni, vedere [Distribuire le chat room di Microsoft Teams con Skype for Business Server](with-skype-for-business-server-2015.md)
    
- Distribuzioni ibride: l'organizzazione ha una combinazione di servizi, con alcuni ospitati in locale e altri online tramite Microsoft 365 o Office 365. Con Microsoft Teams Rooms sono supportati gli scenari ibridi seguenti:
    
  - Exchange Online con Skype for Business Server locale. Per altre informazioni, vedere [Distribuire le chat room di Microsoft Teams con Exchange Online (ibrido).](with-exchange-online.md)
    
  - Exchange locale con Microsoft Teams o Skype for Business online. Per altre informazioni, vedere [Distribuire le chat room di Microsoft Teams con Exchange locale (ibrido).](with-exchange-on-premises.md)
    
La configurazione in uso influisce sulla modalità di preparazione per la configurazione del dispositivo.
  
Alle sale di Microsoft Teams deve essere assegnato un "account del dispositivo" in Active Directory, Exchange e Skype for Business. L'account viene usato per accedere al calendario delle riunioni e stabilire la connettività di Microsoft Teams o Skype for Business. Gli utenti possono prenotare questo account pianificando una riunione con esso. Le sale di Microsoft Teams potranno partecipare alla riunione e fornire varie funzionalità ai partecipanti alla riunione.
  
> [!IMPORTANT]
> Senza un account del dispositivo, nessuna di queste funzionalità funzionerà. 
  
Ogni account del dispositivo è univoco per un singolo dispositivo Microsoft Teams Rooms e richiede alcune impostazioni:
  
- L'account del dispositivo deve essere configurato correttamente.
    
- L'infrastruttura deve essere configurata per consentire a Microsoft Teams Rooms di convalidare l'account del dispositivo e di raggiungere i servizi Microsoft appropriati.
    
> [!IMPORTANT]
> È consigliabile che la creazione dell'account sia eseguita con largo anticipo dell'installazione hardware effettiva. Idealmente, la preparazione dell'account viene avviata due o tre settimane prima dell'installazione. 

Negli ambienti ibridi l'account usato per le chat room di Microsoft Teams deve avere la sincronizzazione delle password abilitata in Azure Active Directory (AAD) Sync perché l'autenticazione di Microsoft Teams Rooms richiede l'autenticazione di Microsoft 365 o Office 365. Quando si configura l'account, assicurarsi che l'indirizzo SIP dell'account corrisponda al relativo nome dell'entità utente (UPN) in AAD. 
  
È possibile pensare a un account del dispositivo come all'account delle risorse che gli utenti riconoscono come l'account di una sala riunioni o dell'area riunioni. Quando si vuole pianificare una riunione usando la sala riunioni, si invita l'account alla riunione. Per usare le chat room di Microsoft Teams in modo più efficace, è necessario eseguire la stessa operazione con l'account del dispositivo assegnato a ognuna di queste.
  
Se per l'area riunioni in cui si sta installando Microsoft Teams Rooms è già configurato un account della cassetta postale delle risorse, è possibile modificare l'account della risorsa in un account del dispositivo. Al termine, è necessario aggiungere l'account del dispositivo a un dispositivo Microsoft Teams Rooms. Vedere gli esempi di configurazione dell'account del dispositivo forniti di seguito.
  
Con un'ulteriore configurazione, la gestione remota è possibile usando Monitor di Microsoft Azure, come descritto in Pianificare la gestione delle sale di Microsoft Teams con [Monitor di Azure,](azure-monitor-plan.md)Distribuire la gestione delle sale di Microsoft Teams con [Monitor di Azure](azure-monitor-deploy.md)e Gestire i dispositivi di Microsoft Teams Rooms con Monitor [di Azure.](azure-monitor-manage.md) 
  
## <a name="basic-configuration"></a>Configurazione di base

Queste proprietà rappresentano la configurazione minima per l'uso di un account del dispositivo con Microsoft Teams Rooms. L'account del dispositivo potrebbe richiedere un'ulteriore configurazione.
  
|**Proprietà**|**Scopo**|
|:-----|:-----|
|Cassetta postale di Exchange (Exchange 2013 SP1 o versione successiva o Exchange Online)  <br/> |L'abilitazione dell'account con una cassetta postale di Exchange offre all'account del dispositivo la possibilità di ricevere e inviare sia messaggi di posta elettronica che convocazioni di riunione e di visualizzare un calendario delle riunioni nel dispositivo Microsoft Teams Rooms. La cassetta postale di Microsoft Teams Rooms deve essere una cassetta postale sala.  <br/> |
|Skype for Business è abilitato  <br/> |Skype for Business deve essere abilitato per poter usare varie funzionalità di conferenza, come videochiamate, messaggistica istantanea e condivisione dello schermo. Sono supportati sia Skype for Business Online che Skype for Business Server.  <br/> |
|Password abilitata  <br/> |L'account del dispositivo deve essere abilitato con una password o non può eseguire l'autenticazione con Exchange o Skype for Business Server.  <br/> |
   
## <a name="advanced-configuration"></a>Configurazione avanzata

Anche se le proprietà per la configurazione di base consentono di configurare l'account del dispositivo in un ambiente semplice, è possibile che l'ambiente abbia altre restrizioni sugli account della directory che devono essere rispettate per consentire a Microsoft Teams Rooms di usare correttamente l'account del dispositivo.
  
|**Proprietà**|**Scopo**|
|:-----|:-----|
|Autenticazione basata su certificati  <br/> |Potrebbero essere necessari certificati sia per Exchange che per Skype for Business Server. Per distribuire i certificati, è possibile caricarli quando si è connessi come amministratore.  <br/> |
   
Il modo più semplice per configurare gli account dei dispositivi è configurarli usando gli account Windows PowerShell. Microsoft fornisce [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), uno script che consente di creare nuovi account del dispositivo o di convalidare gli account delle risorse esistenti per poterli trasformare in account di dispositivi di Microsoft Teams Rooms compatibili.
  
Se si preferisce usare l'interfaccia utente di Microsoft 365 o Office 365 Windows PowerShell cmdlet, è possibile eseguire manualmente alcuni passaggi. Vedere [Creazione di un account del dispositivo con Microsoft 365 o Office 365.](/surface-hub/create-a-device-account-using-office-365)
  
## <a name="see-also"></a>Vedere anche

[Piano per Microsoft Teams Rooms](rooms-plan.md)
  
[Configurare una console per Microsoft Teams Rooms](console.md)
  
[Gestire Microsoft Teams Rooms](rooms-manage.md).