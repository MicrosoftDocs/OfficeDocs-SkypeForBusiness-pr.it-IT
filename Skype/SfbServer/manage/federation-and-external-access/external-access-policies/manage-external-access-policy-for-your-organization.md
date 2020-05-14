---
title: Gestire i criteri di accesso esterno per l'organizzazione
ms.reviewer: ''
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Dopo avere distribuito uno o più server Edge Server, è necessario abilitare i tipi di accesso esterno da supportare per l'organizzazione.
ms.openlocfilehash: e3feecfffa591df5433ce45526ec236ca6ef8b42
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221660"
---
# <a name="manage-external-access-policy-for-your-organization"></a>Gestire i criteri di accesso esterno per l'organizzazione

Dopo avere distribuito uno o più server Edge Server, è necessario abilitare i tipi di accesso esterno da supportare per l'organizzazione.

Per impostazione predefinita, non vi sono criteri configurati per supportare l'accesso utente esterno, inclusi l'accesso utente remoto e federato, anche se il supporto dell'accesso utente esterno è già stato abilitato per l'organizzazione. Per controllare l'uso dell'accesso utente esterno, è necessario configurare uno o più criteri, specificando il tipo di accesso utente esterno supportato per ogni criterio. Per la creazione e la configurazione sono disponibili gli ambiti di criteri seguenti. Per impostazione predefinita, i criteri globali possono essere creati ma non possono essere eliminati.

  - **Criteri globali**   I criteri globali vengono creati quando si distribuiscono i server Edge Server. Per impostazione predefinita, nei criteri globali non vengono abilitate opzioni di accesso per gli utenti esterni. Per supportare l'accesso degli utenti esterni a livello globale, è possibile configurare i criteri globali in modo da supportare uno o più tipi di opzioni di accesso degli utenti esterni. I criteri globali si applicano a tutti gli utenti dell'organizzazione, ma i criteri sito e i criteri utente sostituiscono i criteri globali. Se si eliminano i criteri globali, questi non vengono rimossi, ma ne vengono ripristinate le impostazioni predefinite.

  - **Criteri sito**   È possibile creare e configurare uno o più criteri sito per limitare il supporto per l'accesso degli utenti esterni a siti specifici. La configurazione nel criterio sito ha la priorità sul criterio globale, ma solo per il sito specifico a cui si applica il criterio sito. Se ad esempio si abilita l'accesso degli utenti remoti nel criterio globale, è possibile specificare un criterio sito che disabilita l'accesso degli utenti remoti per un sito specifico. Per impostazione predefinita, un criterio sito viene applicato a tutti gli utenti del sito, ma è possibile assegnare un criterio utente a un utente per ignorare l'impostazione del criterio sito.

  - **Criteri utente**   È possibile creare e configurare uno o più criteri utente per limitare il supporto per l'accesso degli utenti remoti a utenti specifici. La configurazione nel criterio utente ha la priorità sui criteri globale e sito, ma solo per gli utenti specifici a cui viene assegnato il criterio utente. Se ad esempio si abilita l'accesso degli utenti remoti nei criteri globale e sito, è possibile specificare un criterio utente che disabilita l'accesso degli utenti remoti e quindi assegnare tale criterio utente a utenti specifici. Se si crea un criterio utente, è necessario applicarlo a uno o più utenti per renderlo effettivo.


> [!IMPORTANT]  
> Le impostazioni criteri applicate a un determinato livello di criteri possono sostituire le impostazioni applicate a un altro livello di criteri. La precedenza dei criteri di Skype for Business Server è la seguente: i criteri utente (maggiore influenza) sostituiscono i criteri sito e i criteri sito sostituiscono i criteri globali (minore influenza). Ciò significa che maggiore è la prossimità dell'impostazione criteri all'oggetto su cui influiscono i criteri, maggiore è l'influenza su tale oggetto.


Queste opzioni includono i tipi di accesso esterno seguenti:

  - **Abilita comunicazioni con utenti federati**   Abilitare questa opzione se si desidera supportare l'accesso utente ai domini dei partner federati. Questa impostazione consente di configurare la possibilità per gli utenti di comunicare con altri domini federati SIP, nonché di provider ospitati come Microsoft 365 o Office 365. 


  - **Abilita comunicazioni con utenti remoti**   Abilitare questa opzione se si vuole consentire la connessione a Skype for Business Server via Internet agli utenti dell'organizzazione che si trovano all'esterno del firewall, come telelavoratori e utenti in viaggio.

  - **Abilita comunicazioni con utenti pubblici**   Abilitare questa opzione se si vuole consentire agli utenti interni di comunicare con i contatti dei provider di messaggistica istantanea pubblici.
   

> [!NOTE]  
> Oltre ad abilitare il supporto dell'accesso a utenti esterni, è inoltre necessario configurare i criteri per controllare l'uso dell'accesso agli utenti esterni nell'organizzazione prima che sia disponibile qualsiasi tipo di accesso esterno per gli utenti. Per informazioni dettagliate sulla creazione, la configurazione e l'applicazione di criteri per l'accesso agli utenti esterni, vedere [Abilitare o disabilitare l'accesso utente remoto](../access-edge/enable-or-disable-remote-user-access.md).



**Per visualizzare i criteri di accesso esterno usando i cmdlet di Windows PowerShell**

  - È possibile visualizzare i criteri di accesso esterno con Skype for Business Server Management Shell e il **cmdlet Get-CsExternalAccessPolicy**. È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 
    
    Per visualizzare informazioni su tutti i criteri di accesso esterno, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:
    
    `Get-CsExternalAccessPolicy`
    
    Il comando restituisce informazioni simili a quelle riportate di seguito:
    
    ```console
    Identity                          : Global
    Description                       :
    EnableFederationAccess            : False
    EnableXmppAccess                  : False
    EnablePublicCloudAccess           : False
    EnablePublicCloudAudioVideoAccess : False
    EnableOutsideAccess               : False
    ```
