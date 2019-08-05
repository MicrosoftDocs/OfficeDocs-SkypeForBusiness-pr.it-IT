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
localization_priority: Normal
description: Dopo aver distribuito uno o più server perimetrali, è necessario abilitare i tipi di accesso esterno che verranno supportati per l'organizzazione.
ms.openlocfilehash: 014077fb331bc33933d0c673771f7765b9341570
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188807"
---
# <a name="manage-external-access-policy-for-your-organization"></a>Gestire i criteri di accesso esterno per l'organizzazione

Dopo aver distribuito uno o più server perimetrali, è necessario abilitare i tipi di accesso esterno che verranno supportati per l'organizzazione.

Per impostazione predefinita, non sono configurati criteri per supportare l'accesso degli utenti esterni, incluso l'accesso degli utenti remoti, l'accesso degli utenti federati, anche se è già stato abilitato il supporto per l'accesso degli utenti esterni per l'organizzazione. Per controllare l'uso dell'accesso degli utenti esterni, è necessario configurare uno o più criteri, specificando il tipo di accesso utente esterno supportato per ogni criterio. Gli ambiti di criteri seguenti sono disponibili per la creazione e la configurazione. Per impostazione predefinita, il criterio globale viene creato, ma non può essere eliminato.

  - **Criteri globali il**   criterio globale viene creato quando si distribuisce un server perimetrale. Per impostazione predefinita, nel criterio globale non sono abilitate le opzioni di accesso degli utenti esterni. Per supportare l'accesso degli utenti esterni a livello globale, è possibile configurare il criterio globale per supportare uno o più tipi di opzioni di accesso degli utenti esterni. Il criterio globale si applica a tutti gli utenti dell'organizzazione, ma i criteri del sito e i criteri degli utenti eseguono l'override del criterio globale. Se elimini il criterio globale, non lo Rimuovi. Puoi invece reimpostarla sull'impostazione predefinita.

  - **Criteri sito è**   possibile creare e configurare uno o più criteri del sito per limitare il supporto per l'accesso degli utenti esterni a siti specifici. La configurazione dei criteri sito ha la precedenza sui criteri globali, ma solo per il sito specifico a cui i criteri si riferiscono. Ad esempio, se si Abilita l'accesso degli utenti remoti nel criterio globale, è possibile specificare un criterio per il sito che disabilita l'accesso degli utenti remoti per un sito specifico. Per impostazione predefinita, un criterio del sito viene applicato a tutti gli utenti del sito, ma è possibile assegnare un criterio utente a un utente per ignorare l'impostazione dei criteri del sito.

  - **Criteri**   per gli utenti è possibile creare e configurare uno o più criteri utente per limitare il supporto per l'accesso degli utenti remoti a un utente specifico. La configurazione nel criterio utente sostituisce il criterio globale e del sito, ma solo per gli utenti specifici a cui è assegnato il criterio utente. Ad esempio, se si Abilita l'accesso degli utenti remoti nei criteri globali e nei criteri del sito, è possibile specificare un criterio utente che disabilita l'accesso degli utenti remoti e quindi assegnare i criteri utente a utenti specifici. Se crei un criterio utente, devi applicarlo a uno o più utenti prima che abbia effetto.


> [!IMPORTANT]  
> Le impostazioni dei criteri applicate a un livello di criteri possono eseguire l'override delle impostazioni applicate a un altro livello di criteri. La precedenza dei criteri di Skype for Business Server è: criteri utente (la maggior parte delle influenze) esegue l'override di un criterio del sito e quindi un criterio del sito sostituisce un criterio globale (almeno l'influenza). Ciò significa che l'impostazione del criterio è più vicina all'oggetto che il criterio sta influenzando, più influenza ha sull'oggetto.


Queste opzioni includono i tipi di accesso esterno seguenti:

  - **Abilitare le comunicazioni con gli utenti**   federati abilitare questa operazione se si vuole supportare l'accesso degli utenti ai domini partner federati. Questa impostazione configura la possibilità per gli utenti di comunicare con altri domini federati SIP, nonché di provider ospitati come Microsoft Office 365. 


  - **Abilitare le comunicazioni con gli utenti**   remoti abilitare questa opzione se si vuole che gli utenti dell'organizzazione che si trovano all'esterno del firewall, ad esempio i telelavoratori e gli utenti che viaggiano, possano connettersi a Skype for Business Server tramite Internet.

  - **Abilitare le comunicazioni con gli utenti**   pubblici abilitare questa opzione se si vuole che gli utenti interni possano comunicare con i contatti del provider di messaggistica istantanea pubblica.
   

> [!NOTE]  
> Oltre ad abilitare il supporto per l'accesso degli utenti esterni, devi anche configurare i criteri per controllare l'uso dell'accesso degli utenti esterni nell'organizzazione prima che qualsiasi tipo di accesso utente esterno sia disponibile per gli utenti. Per informazioni dettagliate sulla creazione, la configurazione e l'applicazione di criteri per l'accesso degli utenti esterni, vedere [abilitare o disabilitare l'accesso remoto agli utenti](../access-edge/enable-or-disable-remote-user-access.md).



**Per visualizzare i criteri di accesso esterno usando i cmdlet di Windows PowerShell**

  - Puoi visualizzare i criteri di accesso esterno usando Skype for Business Server Management Shell e il cmdlet **Get-CsExternalAccessPolicy** . Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 
    
    Per visualizzare informazioni su tutti i criteri di accesso esterno, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:
    
    `Get-CsExternalAccessPolicy`
    
    Questo comando restituisce informazioni simili a quelle seguenti:
    
    ```
    Identity                          : Global
    Description                       :
    EnableFederationAccess            : False
    EnableXmppAccess                  : False
    EnablePublicCloudAccess           : False
    EnablePublicCloudAudioVideoAccess : False
    EnableOutsideAccess               : False
    ```
