---
title: Assegnare i criteri di conferenza per supportare gli utenti anonimi
ms.reviewer: ''
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Puoi controllare chi può invitare utenti anonimi configurando un criterio di conferenza per supportare utenti anonimi e applicando i criteri di conferenza a utenti specifici.
ms.openlocfilehash: d7956e68db3330f0804e6161e0eeaf52958bc588
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188900"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a>Assegnare criteri di conferenza per supportare utenti anonimi in Skype for Business Server 


Per impostazione predefinita, a tutti gli utenti viene impedito di invitare utenti anonimi a partecipare a una riunione. Puoi controllare chi può invitare utenti anonimi configurando un criterio di conferenza per supportare utenti anonimi e applicando i criteri di conferenza a utenti specifici. Per informazioni dettagliate su come configurare i criteri di conferenza per il supporto degli utenti anonimi, vedere [creare criteri di conferenza in Skype for Business Server](../../conferencing/create-policies.md) e [gestire la Federazione e l'accesso esterno a Skype for Business Server](../managing-federation-and-external-access.md).

Usare la procedura descritta in questa sezione per applicare un criterio di conferenza già creato a uno o più utenti o gruppi di utente.

> [!NOTE]  
> Oltre a configurare e applicare un criterio per consentire agli utenti di invitare utenti anonimi, è anche necessario abilitare il supporto per gli utenti anonimi per l'organizzazione. Per informazioni dettagliate, vedere [configurare i criteri per controllare l'accesso degli utenti pubblici in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a>Per configurare un criterio utente per la partecipazione anonima alle riunioni

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**e quindi eseguire una delle operazioni seguenti:
    
    1.  Per creare un nuovo criterio utente, fare clic su **nuovo**e quindi su **criteri utente**. Creare un nome univoco nel campo **nome** che indichi le informazioni relative ai criteri utente, ad esempio **EnableAnonymous** per un criterio utente che consente la comunicazione con utenti anonimi.
    
    2.  Per configurare un criterio utente esistente, fare clic sul criterio appropriato elencato nella tabella, fare clic su **modifica**e quindi su **Mostra dettagli**.

4.  Nella finestra di dialogo **criteri di conferenza** selezionare la casella **di controllo Consenti ai partecipanti di invitare utenti anonimi** .

5.  Fare clic su **Commit**.

6.  Nella barra di spostamento sinistra fare clic su **utenti**, cercare nell'account utente che si desidera configurare.

7.  Nella tabella in cui sono elencati i risultati della ricerca fare clic sull'account utente, su **Modifica** e quindi su **Mostra dettagli**.

8.  In **modifica utenti di Skype for Business Server** in **criteri di conferenza**Selezionare il criterio utente con la configurazione di accesso utente anonima che si vuole applicare a questo utente.  

    > [!NOTE]  
    > Le <STRONG> &lt;impostazioni&gt; automatiche</STRONG> applicano le impostazioni di installazione predefinite del server e vengono applicate automaticamente dal server.


Per consentire agli utenti di invitare utenti anonimi alle conferenze, è anche necessario abilitare il supporto per gli utenti anonimi dell'organizzazione. Per informazioni dettagliate, vedere [configurare i criteri per controllare l'accesso degli utenti pubblici in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).

