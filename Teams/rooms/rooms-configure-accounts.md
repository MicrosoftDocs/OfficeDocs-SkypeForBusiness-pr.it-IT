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
ms.openlocfilehash: d66e495fd4e1e75227b162974891cda9876fef28c9f809dead001af1a95b099a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54348801"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>Configurare gli account per Microsoft Teams Rooms
 
Leggere questo argomento per informazioni sulle Microsoft Teams Rooms e su come si integra con Exchange e Skype for Business.
  
Questo argomento illustra come creare account usati da Microsoft Teams Rooms in Microsoft Exchange e Skype for Business. Le istruzioni di distribuzione per Microsoft Teams Rooms dispositivi sono trattate in [Configurare una console di Microsoft Teams Rooms.](console.md) È probabile che l'infrastruttura cada in una delle configurazioni seguenti:
  
- Distribuzione online: l'ambiente dell'organizzazione viene distribuito interamente in Microsoft 365 o Office 365. Per altre informazioni, vedere [Distribuire Microsoft Teams Rooms con Microsoft 365 o Office 365](with-office-365.md).
    
- Distribuzione locale: l'organizzazione ha server che controlla, in cui sono ospitati Active Directory, Exchange e Skype for Business Server. Per altre informazioni, vedere [Distribuire Microsoft Teams Rooms con Skype for Business Server](with-skype-for-business-server-2015.md)
    
- Distribuzioni ibride: l'organizzazione ha una combinazione di servizi, con alcuni ospitati in locale e altri online tramite Microsoft 365 o Office 365. Con Microsoft Teams Rooms, sono supportati gli scenari ibridi seguenti:
    
  - Exchange Online con Skype for Business Server locale. Per altre informazioni, vedere [Distribuire Microsoft Teams Rooms con Exchange Online (ibrida)](with-exchange-online.md).
    
  - Exchange locale con Microsoft Teams o Skype for Business Online. Per altre informazioni, vedere [Distribuire Microsoft Teams Rooms con Exchange locale (ibrida).](with-exchange-on-premises.md)
    
La configurazione in uso influisce sulla modalità di preparazione per la configurazione del dispositivo.
  
Microsoft Teams Rooms deve essere assegnato un "account del dispositivo" in Active Directory, Exchange e Skype for Business. L'account viene usato per accedere al calendario della riunione e stabilire Microsoft Teams o Skype for Business connettività. Gli utenti possono prenotare questo account pianificando una riunione con esso. Microsoft Teams Rooms potrà partecipare alla riunione e fornire varie funzionalità ai partecipanti alla riunione.
  
> [!IMPORTANT]
> Senza un account del dispositivo, nessuna di queste funzionalità funzionerà. 
  
Ogni account del dispositivo è univoco per un singolo Microsoft Teams Rooms e richiede una configurazione:
  
- L'account del dispositivo deve essere configurato correttamente.
    
- L'infrastruttura deve essere configurata per consentire Microsoft Teams Rooms convalidare l'account del dispositivo e per raggiungere il servizi Microsoft.
    
> [!IMPORTANT]
> È consigliabile che la creazione dell'account sia eseguita con largo anticipo dell'installazione hardware effettiva. Idealmente, la preparazione dell'account viene avviata due o tre settimane prima dell'installazione. 

Negli ambienti ibridi l'account usato per Microsoft Teams Rooms deve avere la sincronizzazione delle password abilitata nella sincronizzazione Azure Active Directory (AAD) perché l'autenticazione Microsoft Teams Rooms richiede Microsoft 365 o Office 365 autenticazione. Quando si configura l'account, assicurarsi che l'indirizzo SIP dell'account corrisponda al relativo nome dell'entità utente (UPN) in AAD. 
  
È possibile pensare a un account del dispositivo come all'account delle risorse che gli utenti riconoscono come l'account di una sala riunioni o dell'area riunioni. Quando si vuole pianificare una riunione usando la sala riunioni, si invita l'account alla riunione. Per usare le Microsoft Teams Rooms più efficacemente, è necessario eseguire la stessa operazione con l'account del dispositivo assegnato a ognuno di essi.
  
Se si ha già un account della cassetta postale delle risorse configurato per l'area riunioni in cui si sta installando Microsoft Teams Rooms, è possibile modificare l'account della risorsa in un account del dispositivo. Al termine, devi solo aggiungere l'account del dispositivo a un dispositivo Microsoft Teams Rooms dispositivo. Vedere gli esempi di configurazione dell'account del dispositivo forniti di seguito.
  
Con una configurazione aggiuntiva, la gestione remota è possibile usando Microsoft Azure Monitor, come descritto in Pianificare la gestione di Microsoft Teams Rooms con Monitor di [Azure,](azure-monitor-plan.md)Distribuire la gestione [di Microsoft Teams Rooms](azure-monitor-deploy.md)con Monitor di Azure e Gestire i dispositivi Microsoft Teams Rooms con Monitor di [Azure.](azure-monitor-manage.md) 
  
## <a name="basic-configuration"></a>Configurazione di base

Queste proprietà rappresentano la configurazione minima per l'uso di un account del dispositivo Microsoft Teams Rooms. L'account del dispositivo potrebbe richiedere un'ulteriore configurazione.
  
|**Proprietà**|**Scopo**|
|:-----|:-----|
|Exchange cassetta postale (Exchange 2013 SP1 o versione successiva o Exchange Online)  <br/> |L'abilitazione dell'account con una cassetta postale di Exchange consente all'account del dispositivo di ricevere e inviare messaggi di posta elettronica e convocazioni di riunione e di visualizzare un calendario delle riunioni nel dispositivo Microsoft Teams Rooms dispositivo. La Microsoft Teams Rooms cassetta postale deve essere una cassetta postale sala.  <br/> |
|Skype for Business è abilitato  <br/> |Skype for Business deve essere abilitato per poter usare varie funzionalità di conferenza, ad esempio videochiamate, messaggistica istantanea e condivisione dello schermo. Sono supportati Skype for Business online e Skype for Business Server.  <br/> |
|Password abilitata  <br/> |L'account del dispositivo deve essere abilitato con una password o non può eseguire l'autenticazione con Exchange o Skype for Business Server.  <br/> |
   
## <a name="advanced-configuration"></a>Configurazione avanzata

Anche se le proprietà per la configurazione di base consentono di configurare l'account del dispositivo in un ambiente semplice, è possibile che l'ambiente abbia altre restrizioni sugli account della directory che devono essere rispettate per consentire a Microsoft Teams Rooms di usare correttamente l'account del dispositivo.
  
|**Proprietà**|**Scopo**|
|:-----|:-----|
|Autenticazione basata su certificati  <br/> |Potrebbero essere necessari certificati sia per Exchange che per Skype for Business Server. Per distribuire i certificati, è possibile caricarli quando si è connessi come amministratore.  <br/> |
   
Il modo più semplice per configurare gli account dei dispositivi è configurarli usando gli account Windows PowerShell. Microsoft fornisce [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), uno script che consente di creare nuovi account del dispositivo o di convalidare gli account delle risorse esistenti per poterli trasformare in account Microsoft Teams Rooms compatibili.
  
Se si preferisce usare l'interfaccia Microsoft 365 o Office 365'interfaccia utente Windows PowerShell cmdlet, alcuni passaggi possono essere eseguiti manualmente. Vedere [Creazione di un account del](/surface-hub/create-a-device-account-using-office-365)dispositivo Microsoft 365 o Office 365 .
  
## <a name="see-also"></a>Vedere anche

[Piano per Microsoft Teams Rooms](rooms-plan.md)
  
[Configurare una console per Microsoft Teams Rooms](console.md)
  
[Gestire Microsoft Teams Rooms](rooms-manage.md).