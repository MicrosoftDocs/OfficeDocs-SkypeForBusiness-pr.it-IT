---
title: Configurare i criteri per controllare l'accesso degli utenti remoti
ms.reviewer: ''
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: È possibile configurare uno o più criteri di accesso utente esterno per controllare se gli utenti remoti possono collaborare con utenti Skype for Business Server interni. Per controllare l'accesso degli utenti remoti è possibile configurare criteri a livello globale, di sito e di utente.
ms.openlocfilehash: a060622919fb8d948b55178a8e0b1d4da8b6e5cc
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60847289"
---
# <a name="configure-policies-to-control-remote-user-access-in-skype-for-business-server"></a>Configurare i criteri per controllare l'accesso degli utenti remoti in Skype for Business Server

È possibile configurare uno o più criteri di accesso utente esterno per controllare se gli utenti remoti possono collaborare con utenti Skype for Business Server interni. Per controllare l'accesso degli utenti remoti è possibile configurare criteri a livello globale, di sito e di utente. I criteri a livello di sito hanno la priorità sui criteri globali e i criteri utente hanno la priorità sui criteri a livello di sito e globali. Per informazioni dettagliate sui tipi di criteri che è possibile configurare, vedere [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md). Skype for Business Server impostazioni dei criteri applicate a un livello di criteri possono sostituire le impostazioni applicate a un altro livello di criteri. La precedenza dei criteri di Skype for Business Server è la seguente: i criteri utente (maggiore influenza) sostituiscono i criteri sito e i criteri sito sostituiscono i criteri globali (minore influenza). Ciò significa che maggiore è la prossimità dell'impostazione criteri all'oggetto su cui influiscono i criteri, maggiore è l'influenza su tale oggetto.

> [!NOTE]  
> È possibile configurare criteri per il controllo dell'accesso degli utenti remoti anche se non si è abilitato l'accesso utente remoto per l'organizzazione. I criteri configurati, tuttavia, verranno applicati solo dopo l'abilitazione dell'accesso utente remoto per l'organizzazione. Inoltre, se si specifica un criterio utente per controllare l'accesso degli utenti remoti, il criterio si applica solo agli utenti abilitati per Skype for Business Server e configurati per l'utilizzo del criterio. Per informazioni dettagliate sulla specifica degli utenti che possono accedere a Skype for Business Server da posizioni [remote,](assign-an-external-user-access-policy.md)vedere Assign an external user access policy .

Eseguire la procedura seguente per configurare ogni criterio di accesso esterno che si desidera utilizzare per controllare l'accesso degli utenti remoti.


> [!NOTE]  
> Questa procedura descrive come configurare un criterio solo per abilitare le comunicazioni con gli utenti remoti, ma qualsiasi criterio configurato per il supporto dell'accesso utente remoto può configurare anche l'accesso degli utenti federati e l'accesso degli utenti pubblici. Per informazioni dettagliate sulla configurazione dei criteri per supportare gli utenti federati, vedere [Configure policies to control federated user access in Skype for Business Server](configure-policies-to-control-federated-user-access.md). Per informazioni dettagliate sulla configurazione dei criteri per supportare gli utenti pubblici, vedere [Manage SIP federated providers for your organization in Skype for Business Server](../sip-providers/manage-sip-federated-providers-for-your-organization.md).


## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a>Per configurare un criterio di accesso esterno per il supporto dell'accesso utente remoto

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il Skype for Business Server di controllo. 

3.  Sulla barra di spostamento sinistra fare clic su **Accesso utente esterno** e quindi su **Criteri di accesso esterno**.

4.  Nella pagina **Criteri di accesso esterno** eseguire una delle operazioni seguenti:
    
      - Per configurare il criterio globale per il supporto dell'accesso utente remoto, fare clic sul criterio globale, su **Modifica** e quindi su **Mostra dettagli**.
    
      - Per creare nuovi criteri di sito, fare clic su **Nuovo** e quindi su **Criteri sito**. In **Seleziona un sito** fare clic sul sito appropriato nell'elenco e quindi fare clic su **OK**.
    
      - Per creare nuovi criteri utente, fare clic su **Nuovo** e quindi su **Criteri utente**. In **Nuovi criteri di accesso esterno** creare un nome univoco nel campo **Nome** che indichi lo scopo del criterio, ad esempio **AbilitaUtentiRemoti** per un criterio utente che abilita le comunicazioni per gli utenti remoti.
    
      - Per modificare criteri esistenti, fare clic sui criteri appropriati indicati nella tabella, fare clic su **Modifica** e quindi fare clic su **Mostra dettagli**.

5.  (Facoltativo) Se si desidera aggiungere o modificare una descrizione, specificare le informazioni per i criteri in **Descrizione**.

6.  Eseguire una delle operazioni seguenti:
    
      - Per abilitare l'accesso utente remoto per il criterio, selezionare la casella di controllo **Abilita comunicazioni con utenti remoti**.
    
      - Per disabilitare l'accesso utente remoto per il criterio, deselezionare la casella di controllo **Abilita comunicazioni con utenti remoti**.

7.  Fare clic su **Commit**.

Per abilitare l'accesso utente remoto è necessario abilitare anche il supporto dell'accesso utente remoto nell'organizzazione. Per informazioni dettagliate, vedere [Abilitare o disabilitare la federazione e la connettività di messaggistica istantanea pubblica.](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

Se si tratta di un criterio utente è inoltre necessario applicare il criterio agli utenti ai quali si desidera consentire di effettuare l'accesso in remoto. Per informazioni dettagliate, vedere [Assign an external user access policy](assign-an-external-user-access-policy.md).
