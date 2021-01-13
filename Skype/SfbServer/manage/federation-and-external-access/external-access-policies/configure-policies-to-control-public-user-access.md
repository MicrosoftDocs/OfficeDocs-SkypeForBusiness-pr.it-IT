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
localization_priority: Normal
description: la connettività di messaggistica istantanea di UBLIC consente agli utenti dell'organizzazione di utilizzare la messaggistica istantanea per comunicare con gli utenti dei servizi di messaggistica istantanea forniti dai provider di servizi di messaggistica istantanea pubblica.
ms.openlocfilehash: 28bb1c94cb42068fe99f07a6608a3ac1c50991ad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823592"
---
# <a name="configure-policies-to-control-public-user-access-in-skype-for-business-server"></a>Configurazione dei criteri per il controllo dell'accesso degli utenti pubblici in Skype for Business Server

La connettività di messaggistica istantanea pubblica consente agli utenti dell'organizzazione di utilizzare la messaggistica istantanea per comunicare con gli utenti dei servizi di messaggistica istantanea forniti dai provider di servizi di messaggistica istantanea pubblica. È possibile configurare uno o più criteri di accesso utente esterno per controllare se gli utenti pubblici possono collaborare con gli utenti interni di Skype for Business Server. La connettività per la messaggistica istantanea pubblica è una funzionalità aggiunta che si basa sulla configurazione della distribuzione e degli utenti. Dipende anche dal provisioning del servizio nel provider di messaggistica istantanea pubblico. 

Per controllare l'accesso degli utenti pubblici, è possibile configurare i criteri a livello globale, di sito e di utente. Le impostazioni dei criteri di Skype for Business Server applicate a un livello di criteri possono sovrascrivere le impostazioni applicate a un altro livello di criteri. La precedenza dei criteri di Skype for Business Server è la seguente: i criteri utente (maggiore influenza) sostituiscono i criteri sito e i criteri sito sostituiscono i criteri globali (minore influenza). Ciò significa che maggiore è la prossimità dell'impostazione criteri all'oggetto su cui influiscono i criteri, maggiore è l'influenza su tale oggetto.

Nel caso degli inviti di messaggistica istantanea, la risposta dipende dal software client. La richiesta viene accettata, a meno che i mittenti esterni siano esplicitamente bloccati da una regola configurata dall'utente, ovvero le impostazioni negli elenchi **Consenti** e **blocca** client dell'utente. Inoltre, gli inviti di messaggistica istantanea possono essere bloccati se un utente decide di bloccare tutti i messaggi istantanei provenienti da utenti che non sono presenti nell'elenco **Consenti** .



> [!NOTE]  
> È possibile configurare i criteri per controllare l'accesso degli utenti pubblici, anche se non è stata abilitata la Federazione per l'organizzazione. I criteri configurati, tuttavia, verranno applicati solo dopo aver abilitato la federazione per l'organizzazione. Per informazioni dettagliate sull'abilitazione della Federazione, vedere [abilitare o disabilitare l'accesso degli utenti remoti](../access-edge/enable-or-disable-remote-user-access.md). Inoltre, se si specifica un criterio utente per controllare l'accesso degli utenti pubblici, il criterio si applica solo agli utenti abilitati per Skype for Business Server e configurati per l'utilizzo del criterio. Per informazioni dettagliate sulla specifica degli utenti pubblici che possono accedere a Skype for Business Server, vedere [assegnare un criterio di accesso utente esterno](assign-an-external-user-access-policy.md).


Utilizzare la procedura seguente per configurare un criterio per il supporto dell'accesso da parte di utenti di uno o più provider di messaggistica istantanea pubblica.

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a>Per configurare un criterio di accesso esterno per il supporto dell'accesso degli utenti pubblici

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **Accesso utente esterno** e quindi su **Criteri di accesso esterno**.

4.  Nella pagina **Criteri di accesso esterno** eseguire una delle operazioni seguenti:
    
      - Per configurare i criteri globali per il supporto dell'accesso degli utenti pubblici, fare clic sul criterio globale, fare clic su **modifica** e quindi su **Mostra dettagli**.
    
      - Per creare un nuovo criterio sito fare clic su **Nuovo** e quindi su **Criteri sito**. In **Seleziona un sito** fare clic sul sito appropriato nell'elenco e quindi su **OK**.
    
      - Per creare nuovi criteri utente, fare clic su **Nuovo** e quindi su **Criteri utente**. In **nuovi criteri di accesso esterno**, creare un nome univoco nel campo **nome** che indica le coperture dei criteri utente, ad esempio **EnablePublicUsers** per i criteri utente che abilitano le comunicazioni per gli utenti pubblici.
    
      - Per modificare criteri esistenti, fare clic sui criteri appropriati indicati nella tabella, fare clic su **Modifica** e quindi fare clic su **Mostra dettagli**.

5.  (Facoltativo) Se si desidera aggiungere o modificare una descrizione, specificare le informazioni per i criteri in **Descrizione**.

6.  Eseguire una delle operazioni seguenti:
    
      - Per abilitare l'accesso degli utenti pubblici per i criteri, selezionare la casella di controllo **Abilita comunicazioni con utenti pubblici** .
    
      - Per disabilitare l'accesso degli utenti pubblici per i criteri, deselezionare la casella di controllo **Abilita comunicazioni con utenti pubblici** .

7.  Fare clic su **Commit**.

Per abilitare l'accesso degli utenti pubblici, è necessario abilitare anche il supporto della federazione nell'organizzazione. Per ulteriori informazioni, vedere [Configure policies to Control Federated User Access in Skype for Business Server](configure-policies-to-control-federated-user-access.md).

Se si tratta di un criterio utente, è inoltre necessario applicare il criterio agli utenti pubblici che si desidera consentire la collaborazione con gli utenti pubblici. 


## <a name="see-also"></a>Vedere anche

[Gestire i provider federati SIP per l'organizzazione](../sip-providers/manage-sip-federated-providers-for-your-organization.md)
