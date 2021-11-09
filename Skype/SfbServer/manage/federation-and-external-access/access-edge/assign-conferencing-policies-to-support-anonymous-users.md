---
title: Assegnare criteri di conferenza per supportare gli utenti anonimi
ms.reviewer: ''
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
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
description: È possibile decidere chi può invitare utenti anonimi configurando un criterio di conferenza che li supporti e applicando tale criterio a utenti specifici.
ms.openlocfilehash: 25762861b6086750213553bca9bfd02dab01187d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60848499"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a>Assegnare criteri di conferenza per supportare gli utenti anonimi in Skype for Business Server 


Per impostazione predefinita, a tutti gli utenti è proibito invitare utenti anonimi a partecipare a una riunione. È possibile decidere chi può invitare utenti anonimi configurando un criterio di conferenza che li supporti e applicando tale criterio a utenti specifici. Per informazioni dettagliate su come configurare criteri di conferenza per supportare gli utenti anonimi, vedere [Create conferencing policies in Skype for Business Server](../../conferencing/create-policies.md) e Managing federation and external access to [Skype for Business Server](../managing-federation-and-external-access.md).

Utilizzare la procedura in questa sezione per applicare criteri di conferenza già creati a uno o più utenti o gruppi di utenti.

> [!NOTE]  
> Oltre alla configurazione e all'applicazione di criteri per consentire agli utenti di invitare utenti anonimi, è inoltre necessario abilitare il supporto degli utenti anonimi per l'organizzazione. Per informazioni dettagliate, vedere [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a>Per configurare i criteri utente per la partecipazione anonima alle riunioni

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il Skype for Business Server di controllo. 

3.  Sulla barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi eseguire una delle operazioni seguenti:
    
    1.  Per creare nuovi criteri utente, fare clic su **Nuovo** e quindi su **Criteri utente**. Creare un nome univoco nel campo **Nome** che indichi lo scopo dei criteri, ad esempio **AbilitaAnonimi** per criteri utente per l'abilitazione delle comunicazioni per gli utenti anonimi.
    
    2.  Per configurare criteri utente esistenti, fare clic sui criteri appropriati indicati nella tabella, fare clic su **Modifica** e quindi fare clic su **Mostra dettagli**.

4.  Nella finestra di dialogo **Criteri conferenza** selezionare la casella di controllo **Consenti ai partecipanti di invitare utenti anonimi**.

5.  Fare clic su **Commit**.

6.  Sulla barra di spostamento sinistra fare clic su **Utenti** e quindi cercare l'account utente che si desidera configurare.

7.  Nella tabella dei risultati di ricerca fare clic sull'account utente, fare clic su **Modifica** e quindi fare clic su **Mostra dettagli**.

8.  In **Modifica Skype for Business Server utente** **in** Criteri conferenza selezionare il criterio utente con la configurazione di accesso utente anonimo che si desidera applicare all'utente.  

    > [!NOTE]  
    > Le <STRONG> &lt; impostazioni &gt; </STRONG> automatiche applicano le impostazioni di installazione predefinite del server e vengono applicate automaticamente dal server.


Per consentire agli utenti di invitare utenti anonimi alle conferenze, è inoltre necessario abilitare il supporto per gli utenti anonimi nell'organizzazione. Per informazioni dettagliate, vedere [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).

