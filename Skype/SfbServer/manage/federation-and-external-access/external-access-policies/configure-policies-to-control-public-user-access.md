---
title: Configurare criteri per controllare l'accesso degli utenti pubblici
ms.reviewer: ''
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
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
description: la connettività di messaggistica istantanea di UBLIC consente agli utenti della propria organizzazione di usare la messaggistica istantanea per comunicare con gli utenti dei servizi di messaggistica istantanea forniti dai provider di servizi di messaggistica istantanea pubblici.
ms.openlocfilehash: d661ca9a4ef7840cbc955d0c999ae5a1490a63cb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818307"
---
# <a name="configure-policies-to-control-public-user-access-in-skype-for-business-server"></a>Configurare i criteri per controllare l'accesso degli utenti pubblici in Skype for Business Server

La connettività di messaggistica istantanea pubblica consente agli utenti dell'organizzazione di usare la messaggistica istantanea per comunicare con gli utenti dei servizi di messaggistica istantanea forniti dai provider di servizi di messaggistica istantanea pubblici. Puoi configurare uno o più criteri di accesso degli utenti esterni per controllare se gli utenti pubblici possono collaborare con utenti interni di Skype for Business Server. La connettività di messaggistica istantanea pubblica è una caratteristica aggiunta che si basa sulla configurazione della distribuzione e degli utenti. Dipende anche dal provisioning del servizio presso il provider di messaggistica istantanea pubblica. 

Per controllare l'accesso degli utenti pubblici, è possibile configurare i criteri a livello globale, sito e utente. Le impostazioni dei criteri di Skype for Business Server applicate a un livello di criteri possono eseguire l'override delle impostazioni applicate a un altro livello di criteri. La precedenza dei criteri di Skype for Business Server è: criteri utente (la maggior parte delle influenze) esegue l'override di un criterio del sito e quindi un criterio del sito sostituisce un criterio globale (almeno l'influenza). Ciò significa che l'impostazione del criterio è più vicina all'oggetto che il criterio sta influenzando, più influenza ha sull'oggetto.

In caso di inviti alla messaggistica istantanea, la risposta dipende dal software client. La richiesta viene accettata a meno che i mittenti esterni non siano esplicitamente bloccati da una regola configurata dall'utente, ovvero le impostazioni negli elenchi **Consenti** e **blocca** del client dell'utente. Inoltre, gli inviti di messaggistica istantanea possono essere bloccati se un utente sceglie di bloccare tutti i messaggi istantanei da utenti che non sono presenti nell'elenco **Consenti** .



> [!NOTE]  
> È possibile configurare i criteri per controllare l'accesso degli utenti pubblici, anche se non è stata abilitata la Federazione per l'organizzazione. Tuttavia, i criteri configurati sono attivi solo quando è abilitata la Federazione per l'organizzazione. Per informazioni dettagliate sull'abilitazione della Federazione, vedere [abilitare o disabilitare l'accesso remoto agli utenti](../access-edge/enable-or-disable-remote-user-access.md). Inoltre, se specifichi un criterio utente per controllare l'accesso degli utenti pubblici, il criterio si applica solo agli utenti abilitati per Skype for Business Server e configurati per l'uso dei criteri. Per informazioni dettagliate su come specificare gli utenti pubblici che possono accedere a Skype for Business Server, vedere [assegnare un criterio di accesso degli utenti esterni](assign-an-external-user-access-policy.md).


Usare la procedura seguente per configurare un criterio per supportare l'accesso da parte di utenti di uno o più provider di messaggistica istantanea pubblici.

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a>Per configurare un criterio di accesso esterno per supportare l'accesso degli utenti pubblici

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **accesso utente esterno**e quindi su **criteri di accesso esterno**.

4.  Nella pagina **criteri di accesso esterno** eseguire una delle operazioni seguenti:
    
      - Per configurare il criterio globale per supportare l'accesso degli utenti pubblici, fare clic sul criterio globale, fare clic su **modifica**e quindi su **Mostra dettagli**.
    
      - Per creare un nuovo criterio sito, fare clic su **nuovo**e quindi su **criteri sito**. In **Seleziona un sito**fare clic sul sito appropriato nell'elenco e quindi fare clic su **OK**.
    
      - Per creare un nuovo criterio utente, fare clic su **nuovo**e quindi su **criteri utente**. In **nuovi criteri di accesso esterno**, creare un nome univoco nel campo **nome** che indichi le informazioni relative ai criteri utente, ad esempio **EnablePublicUsers** , per un criterio utente che consente le comunicazioni per gli utenti pubblici.
    
      - Per modificare un criterio esistente, fare clic sul criterio appropriato elencato nella tabella, fare clic su **modifica**e quindi su **Mostra dettagli**.

5.  Opzionale Se si vuole aggiungere o modificare una descrizione, specificare le informazioni per il criterio in **Descrizione**.

6.  Esegui una delle operazioni seguenti:
    
      - Per abilitare l'accesso degli utenti pubblici al criterio, selezionare la casella di controllo **Abilita comunicazioni con gli utenti pubblici** .
    
      - Per disabilitare l'accesso degli utenti pubblici per il criterio, deselezionare la casella di controllo **Abilita comunicazioni con gli utenti pubblici** .

7.  Fare clic su **Commit**.

Per abilitare l'accesso degli utenti pubblici, devi anche abilitare il supporto per la Federazione nell'organizzazione. Per informazioni dettagliate, vedere [configurare i criteri per controllare l'accesso degli utenti federati in Skype for Business Server](configure-policies-to-control-federated-user-access.md).

Se si tratta di un criterio utente, è necessario applicare il criterio anche agli utenti pubblici che si vuole poter collaborare con gli utenti pubblici. 


## <a name="see-also"></a>Vedere anche

[Gestire i provider federati SIP per l'organizzazione](../sip-providers/manage-sip-federated-providers-for-your-organization.md)
