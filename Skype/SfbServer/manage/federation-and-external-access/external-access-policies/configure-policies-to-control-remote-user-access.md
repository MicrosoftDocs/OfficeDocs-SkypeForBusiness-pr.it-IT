---
title: Configurare criteri per controllare l'accesso degli utenti remoti
ms.reviewer: ''
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
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
description: Puoi configurare uno o più criteri di accesso degli utenti esterni per controllare se gli utenti remoti possono collaborare con gli utenti di Skype for Business Server interni. Per controllare l'accesso degli utenti remoti, è possibile configurare i criteri a livello globale, sito e utente.
ms.openlocfilehash: 7735f15e61654f55a70f18ca032cd6b1613fec58
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818297"
---
# <a name="configure-policies-to-control-remote-user-access-in-skype-for-business-server"></a>Configurare i criteri per il controllo dell'accesso degli utenti remoti in Skype for Business Server

Puoi configurare uno o più criteri di accesso degli utenti esterni per controllare se gli utenti remoti possono collaborare con gli utenti di Skype for Business Server interni. Per controllare l'accesso degli utenti remoti, è possibile configurare i criteri a livello globale, sito e utente. I criteri del sito sostituiscono i criteri globali e i criteri utente sostituiscono il sito e i criteri globali. Per informazioni dettagliate sui tipi di criteri che è possibile configurare, vedere [gestione della Federazione e accesso esterno a Skype for Business Server](../managing-federation-and-external-access.md). Le impostazioni dei criteri di Skype for Business Server applicate a un livello di criteri possono eseguire l'override delle impostazioni applicate a un altro livello di criteri. La precedenza dei criteri di Skype for Business Server è: criteri utente (la maggior parte delle influenze) esegue l'override di un criterio del sito e quindi un criterio del sito sostituisce un criterio globale (almeno l'influenza). Ciò significa che l'impostazione del criterio è più vicina all'oggetto che il criterio sta influenzando, più influenza ha sull'oggetto.

> [!NOTE]  
> È possibile configurare i criteri per controllare l'accesso degli utenti remoti, anche se non è stato abilitato l'accesso degli utenti remoti per l'organizzazione. Tuttavia, i criteri configurati sono attivi solo quando si ha accesso a utenti remoti abilitato per l'organizzazione. Inoltre, se specifichi un criterio utente per controllare l'accesso degli utenti remoti, il criterio si applica solo agli utenti abilitati per Skype for Business Server e configurati per l'uso dei criteri. Per informazioni dettagliate su come specificare gli utenti che possono accedere a Skype for Business Server da percorsi remoti, vedere [assegnare criteri di accesso degli utenti esterni](assign-an-external-user-access-policy.md).

Usare la procedura seguente per configurare ogni criterio di accesso esterno che si vuole usare per controllare l'accesso degli utenti remoti.


> [!NOTE]  
> Questa procedura descrive come configurare un criterio solo per abilitare le comunicazioni con gli utenti remoti, ma ogni criterio configurato per supportare l'accesso degli utenti remoti può anche configurare l'accesso degli utenti federati e l'accesso degli utenti pubblici. Per informazioni dettagliate sulla configurazione dei criteri per il supporto degli utenti federati, vedere [configurare i criteri per controllare l'accesso degli utenti federati in Skype for Business Server](configure-policies-to-control-federated-user-access.md). Per informazioni dettagliate sulla configurazione dei criteri per il supporto degli utenti pubblici, vedere [gestire i provider federati SIP per l'organizzazione in Skype for Business Server](../sip-providers/manage-sip-federated-providers-for-your-organization.md).


## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a>Per configurare un criterio di accesso esterno per supportare l'accesso degli utenti remoti

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **accesso utente esterno**e quindi su **criteri di accesso esterno**.

4.  Nella pagina **criteri di accesso esterno** eseguire una delle operazioni seguenti:
    
      - Per configurare i criteri globali per il supporto dell'accesso degli utenti remoti, fare clic sul criterio globale, scegliere **modifica**e quindi fare clic su **Mostra dettagli**.
    
      - Per creare un nuovo criterio sito, fare clic su **nuovo**e quindi su **criteri sito**. In **Seleziona un sito**fare clic sul sito appropriato nell'elenco e quindi fare clic su **OK**.
    
      - Per creare un nuovo criterio utente, fare clic su **nuovo**e quindi su **criteri utente**. In **nuovi criteri di accesso esterno**, creare un nome univoco nel campo **nome** che indichi le informazioni relative ai criteri utente, ad esempio **EnableRemoteUsers** , per un criterio utente che consente le comunicazioni per gli utenti remoti.
    
      - Per modificare un criterio esistente, fare clic sul criterio appropriato elencato nella tabella, fare clic su **modifica**e quindi su **Mostra dettagli**.

5.  Opzionale Se si vuole aggiungere o modificare una descrizione, specificare le informazioni per il criterio in **Descrizione**.

6.  Esegui una delle operazioni seguenti:
    
      - Per abilitare l'accesso degli utenti remoti per il criterio, selezionare la casella di controllo **Abilita comunicazioni con utenti remoti** .
    
      - Per disabilitare l'accesso degli utenti remoti per il criterio, deselezionare la casella di controllo **Abilita comunicazioni con utenti remoti** .

7.  Fare clic su **Commit**.

Per abilitare l'accesso remoto agli utenti, è necessario abilitare anche il supporto per l'accesso degli utenti remoti nell'organizzazione. Per informazioni dettagliate, vedere [abilitare o disabilitare la connettività per la messaggistica istantanea pubblica e la Federazione](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).

Se si tratta di un criterio utente, è necessario applicare il criterio anche agli utenti che si vogliono connettere in remoto. Per informazioni dettagliate, vedere [assegnare criteri di accesso degli utenti esterni](assign-an-external-user-access-policy.md).
