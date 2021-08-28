---
title: Configurare i criteri per controllare l'accesso degli utenti pubblici
ms.reviewer: ''
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: La connettività di messaggistica istantanea consente agli utenti dell'organizzazione di utilizzare la messaggistica istantanea per comunicare con gli utenti dei servizi di messaggistica istantanea forniti dai provider di servizi di messaggistica istantanea pubblici.
ms.openlocfilehash: 13ef277693c219436e37fc2b9ddee8b78ff5ebc0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58625198"
---
# <a name="configure-policies-to-control-public-user-access-in-skype-for-business-server"></a>Configurare i criteri per controllare l'accesso degli utenti pubblici in Skype for Business Server

La connettività di messaggistica istantanea pubblica consente agli utenti dell'organizzazione di utilizzare la messaggistica istantanea per comunicare con gli utenti dei servizi di messaggistica istantanea forniti dai provider di servizi di messaggistica istantanea pubblici. È possibile configurare uno o più criteri di accesso degli utenti esterni per controllare se gli utenti pubblici possono collaborare con utenti Skype for Business Server interni. La connettività di messaggistica istantanea pubblica è una funzionalità aggiunta che si basa sulla configurazione della distribuzione e degli utenti. Dipende anche dal provisioning del servizio presso il provider di messaggistica istantanea pubblico. 

Per controllare l'accesso degli utenti pubblici, è possibile configurare i criteri a livello globale, di sito e di utente. Skype for Business Server impostazioni dei criteri applicate a un livello di criteri possono sostituire le impostazioni applicate a un altro livello di criteri. La precedenza dei criteri di Skype for Business Server è la seguente: i criteri utente (maggiore influenza) sostituiscono i criteri sito e i criteri sito sostituiscono i criteri globali (minore influenza). Ciò significa che maggiore è la prossimità dell'impostazione criteri all'oggetto su cui influiscono i criteri, maggiore è l'influenza su tale oggetto.

Nel caso di inviti di messaggistica istantanea, la risposta dipende dal software client. La richiesta viene accettata a meno che i mittenti esterni non siano esplicitamente bloccati da una regola configurata dall'utente, ovvero le impostazioni negli elenchi Consenti e **Blocca** del **client** dell'utente. Inoltre, gli inviti di messaggistica istantanea possono essere bloccati se un utente sceglie di bloccare tutti i messaggi istantanei provenienti da utenti non presenti nel proprio **elenco Consenti.**



> [!NOTE]  
> È possibile configurare criteri per controllare l'accesso degli utenti pubblici, anche se non è stata abilitata la federazione per l'organizzazione. I criteri configurati, tuttavia, verranno applicati solo dopo aver abilitato la federazione per l'organizzazione. Per informazioni dettagliate sull'abilitazione della federazione, vedere [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md). Inoltre, se si specifica un criterio utente per controllare l'accesso degli utenti pubblici, il criterio si applica solo agli utenti abilitati per Skype for Business Server e configurati per l'utilizzo del criterio. Per informazioni dettagliate sulla specifica di utenti pubblici che possono accedere a Skype for Business Server, vedere [Assign an external user access policy](assign-an-external-user-access-policy.md).


Utilizzare la procedura seguente per configurare un criterio per supportare l'accesso da parte degli utenti di uno o più provider di messaggistica istantanea pubblici.

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a>Per configurare un criterio di accesso esterno per supportare l'accesso degli utenti pubblici

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo. 

3.  Sulla barra di spostamento sinistra fare clic su **Accesso utente esterno** e quindi su **Criteri di accesso esterno**.

4.  Nella pagina **Criteri di accesso esterno** eseguire una delle operazioni seguenti:
    
      - Per configurare il criterio globale per supportare l'accesso degli utenti pubblici, fare clic sul criterio globale, su **Modifica** e quindi **su Mostra dettagli.**
    
      - Per creare un nuovo criterio sito fare clic su **Nuovo** e quindi su **Criteri sito**. In **Seleziona un sito** fare clic sul sito appropriato nell'elenco e quindi su **OK**.
    
      - Per creare nuovi criteri utente, fare clic su **Nuovo** e quindi su **Criteri utente**. In Nuovi criteri di **accesso** esterno creare un nome univoco nel campo **Nome** che indichi il contenuto dei criteri utente, ad esempio **EnablePublicUsers** per un criterio utente che abilita le comunicazioni per gli utenti pubblici.
    
      - Per modificare criteri esistenti, fare clic sui criteri appropriati indicati nella tabella, fare clic su **Modifica** e quindi fare clic su **Mostra dettagli**.

5.  (Facoltativo) Se si desidera aggiungere o modificare una descrizione, specificare le informazioni per i criteri in **Descrizione**.

6.  Eseguire una delle operazioni seguenti:
    
      - Per abilitare l'accesso degli utenti pubblici per il criterio, selezionare la **casella di** controllo Abilita comunicazioni con utenti pubblici.
    
      - Per disabilitare l'accesso degli utenti pubblici per il criterio, deselezionare la **casella di** controllo Abilita comunicazioni con utenti pubblici.

7.  Fare clic su **Commit**.

Per abilitare l'accesso degli utenti pubblici, è necessario abilitare anche il supporto della federazione nell'organizzazione. Per informazioni dettagliate, [vedere Configure policies to control federated user access in Skype for Business Server](configure-policies-to-control-federated-user-access.md).

Se si tratta di un criterio utente, è necessario applicarlo anche agli utenti pubblici che si desidera possano collaborare con gli utenti pubblici. 


## <a name="see-also"></a>Vedere anche

[Gestire i provider federati SIP per l'organizzazione](../sip-providers/manage-sip-federated-providers-for-your-organization.md)
