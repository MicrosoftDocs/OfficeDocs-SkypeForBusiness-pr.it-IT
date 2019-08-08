---
title: Configurare gli account per le sale di Microsoft Teams
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: ''
description: Leggere questo argomento per informazioni su come configurare gli account per Microsoft teams rooms in Exchange e Skype for business.
ms.openlocfilehash: 30e887aa09b9013c3db18fb33133d11c639f9fe8
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243323"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>Configurare gli account per le sale di Microsoft Teams
 
Leggere questo argomento per informazioni sulle sale di Microsoft teams e su come si integra con Exchange e Skype for business.
  
Questo argomento illustra come creare account usati dalle sale di Microsoft teams in Microsoft Exchange e Skype for business. Le istruzioni di distribuzione per i dispositivi Microsoft teams Rooms sono descritte in [configurare una console Microsoft teams Rooms](console.md). L'infrastruttura probabilmente rientrerà in una delle configurazioni seguenti:
  
- Distribuzione online: l'ambiente dell'organizzazione è distribuito interamente in Office 365. Per altre informazioni, vedere [distribuire le sale di Microsoft teams con Office 365](with-office-365.md).
    
- Distribuzione locale: l'organizzazione ha i server che controllano, dove sono ospitati Active Directory, Exchange e Skype for Business Server. Per altre informazioni, vedere [distribuire le sale di Microsoft teams con Skype for Business Server](with-skype-for-business-server-2015.md)
    
- Distribuzioni ibride: l'organizzazione ha una combinazione di servizi, con alcuni ospitati in locale e alcuni ospitati online tramite Office 365. Con le sale di Microsoft teams sono supportati gli scenari ibridi seguenti: 
    
  - Exchange Online con Skype for Business Server in locale. Per altre informazioni, vedere [distribuire le sale di Microsoft teams con Exchange Online (Hybrid)](with-exchange-online.md).
    
  - Exchange in locale con Microsoft teams o Skype for business online. Per altre informazioni, vedere [distribuire le sale di Microsoft teams con Exchange in locale (Hybrid)](with-exchange-on-premises.md).
    
La configurazione che si ha avrà effetto su come prepararsi per la configurazione del dispositivo.
  
A Microsoft teams Rooms deve essere assegnato un "account del dispositivo" in Active Directory, Exchange e Skype for business. L'account viene usato per accedere al calendario della riunione e stabilire la connettività di Microsoft teams o Skype for business. Gli utenti possono prenotare il proprio account con la pianificazione di una riunione. Microsoft teams Rooms sarà in grado di partecipare alla riunione e fornirà varie funzionalità ai partecipanti alla riunione.
  
> [!IMPORTANT]
> Senza un account di dispositivo, nessuna di queste funzionalità funzionerà. 
  
Ogni account di dispositivo è univoco per un singolo dispositivo Microsoft teams Rooms e richiede alcune impostazioni:
  
- L'account del dispositivo deve essere configurato correttamente.
    
- L'infrastruttura deve essere configurata in modo da consentire a Microsoft teams Rooms di convalidare l'account del dispositivo e di raggiungere i servizi Microsoft appropriati.
    
> [!IMPORTANT]
> È vivamente consigliabile che la creazione di account venga eseguita correttamente prima dell'installazione hardware effettiva. Idealmente, la preparazione dell'account viene avviata da due a tre settimane prima dell'installazione. Negli ambienti ibridi l'account usato per le sale di Microsoft Teams deve avere la sincronizzazione delle password abilitata nella sincronizzazione di AAD perché l'autenticazione di Microsoft teams Rooms richiede l'autenticazione di Office 365.
  
Si può pensare a un account del dispositivo come account delle risorse riconosciuto dagli utenti come account della sala riunioni o della riunione. Quando si vuole pianificare una riunione usando quella sala riunioni, si invita l'account a tale riunione. Per usare in modo più efficiente le sale di Microsoft teams, è possibile eseguire la stessa operazione con l'account del dispositivo assegnato a ognuno di essi.
  
Se è già stato configurato un account di cassetta postale per lo spazio riunioni in cui si installano le sale di Microsoft teams, è possibile cambiare l'account di una risorsa in un account di dispositivo. Una volta terminato, tutto quello che devi fare è aggiungere l'account del dispositivo a un dispositivo Microsoft teams rooms. Vedere esempi di configurazione dell'account di dispositivo forniti di seguito.
  
Con la configurazione aggiuntiva, la gestione remota è possibile usando Microsoft Azure monitor come descritto in [pianificare la gestione di Microsoft teams Rooms con Azure monitor](azure-monitor-plan.md), [distribuire Gestione di Microsoft teams Rooms con Azure monitor](azure-monitor-deploy.md)e [ Gestire i dispositivi Microsoft teams Rooms con Azure monitor](azure-monitor-manage.md). 
  
## <a name="basic-configuration"></a>Configurazione di base

Queste proprietà rappresentano la configurazione minima per un account di dispositivo per l'utilizzo con le sale di Microsoft teams. L'account del dispositivo può richiedere ulteriore configurazione.
  
|**Proprietà**|**Scopo**|
|:-----|:-----|
|Cassetta postale di Exchange (Exchange 2013 SP1 o versione successiva o Exchange Online)  <br/> |L'abilitazione dell'account con una cassetta postale di Exchange offre all'account del dispositivo la possibilità di ricevere e inviare sia le convocazioni di posta e riunione che la visualizzazione di un calendario di riunioni nel dispositivo Microsoft teams rooms. La cassetta postale di Microsoft teams Rooms deve essere una cassetta postale della sala.  <br/> |
|Skype for business è abilitato  <br/> |Skype for business deve essere abilitato per l'uso di varie funzionalità di conferenza, come videochiamate, messaggistica istantanea e condivisione dello schermo. Sono supportati sia Skype for business online che Skype for Business Server.  <br/> |
|Abilitato per la password  <br/> |L'account del dispositivo deve essere abilitato con una password oppure non può eseguire l'autenticazione con Exchange o Skype for Business Server.  <br/> |
   
## <a name="advanced-configuration"></a>Configurazione avanzata

Mentre le proprietà per la configurazione di base consentiranno di configurare l'account del dispositivo in un ambiente semplice, è possibile che l'ambiente disponga di altre restrizioni sugli account di directory che devono essere soddisfatte in modo che le sale di Microsoft teams usino correttamente l' account del dispositivo.
  
|**Proprietà**|**Scopo**|
|:-----|:-----|
|Autenticazione basata su certificati  <br/> |I certificati possono essere necessari sia per Exchange che per Skype for Business Server. Per distribuire i certificati, è possibile caricarli durante l'accesso come amministratore.  <br/> |
   
Il modo più semplice per configurare gli account di dispositivo consiste nel configurarli con Windows PowerShell remoto. Microsoft include [SkypeRoomProvisioningScript. ps1](https://go.microsoft.com/fwlink/?linkid=870105), uno script che consente di creare nuovi account di dispositivo o di convalidare gli account di risorse esistenti per consentire di trasformarli in account di dispositivo Microsoft teams compatibili.
  
Se si preferisce usare l'interfaccia utente di Office 365 sui cmdlet di Windows PowerShell, è possibile eseguire manualmente alcuni passaggi. Vedere [creazione di un account di dispositivo tramite Office 365](https://docs.microsoft.com/surface-hub/create-a-device-account-using-office-365).
  
## <a name="see-also"></a>Vedere anche

[Pianificare le sale di Microsoft Teams](skype-room-systems-v2-0.md)
  
[Configurare una console Microsoft teams rooms](console.md)
  
[Gestire le sale di Microsoft Teams](skype-room-systems-v2.md)

