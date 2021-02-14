---
title: Assegnare criteri di conferenza per supportare gli utenti anonimi
ms.reviewer: ''
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
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
description: È possibile decidere chi può invitare utenti anonimi configurando un criterio di conferenza che li supporti e applicando tale criterio a utenti specifici.
ms.openlocfilehash: 57d100569722cbe89811d15eb9fbe04e5d375711
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817456"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a>Assegnare criteri di conferenza per supportare gli utenti anonimi in Skype for Business Server 


Per impostazione predefinita, a tutti gli utenti è proibito invitare utenti anonimi a partecipare a una riunione. È possibile decidere chi può invitare utenti anonimi configurando un criterio di conferenza che li supporti e applicando tale criterio a utenti specifici. Per informazioni dettagliate su come configurare i criteri di conferenza per supportare gli utenti anonimi, vedere Creare criteri di conferenza [in Skype for Business Server](../../conferencing/create-policies.md) e Gestire la federazione e l'accesso esterno a Skype for Business [Server.](../managing-federation-and-external-access.md)

Utilizzare la procedura in questa sezione per applicare criteri di conferenza già creati a uno o più utenti o gruppi di utenti.

> [!NOTE]  
> Oltre alla configurazione e all'applicazione di criteri per consentire agli utenti di invitare utenti anonimi, è inoltre necessario abilitare il supporto degli utenti anonimi per l'organizzazione. Per informazioni dettagliate, vedere [Configurare i criteri per controllare l'accesso degli utenti pubblici in Skype for Business Server.](../external-access-policies/configure-policies-to-control-public-user-access.md)


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a>Per configurare i criteri utente per la partecipazione anonima alle riunioni

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi eseguire una delle operazioni seguenti:
    
    1.  Per creare nuovi criteri utente, fare clic su **Nuovo** e quindi su **Criteri utente**. Creare un nome univoco nel campo **Nome** che indichi lo scopo dei criteri, ad esempio **AbilitaAnonimi** per criteri utente per l'abilitazione delle comunicazioni per gli utenti anonimi.
    
    2.  Per configurare criteri utente esistenti, fare clic sui criteri appropriati indicati nella tabella, fare clic su **Modifica** e quindi fare clic su **Mostra dettagli**.

4.  Nella finestra di dialogo **Criteri conferenza** selezionare la casella di controllo **Consenti ai partecipanti di invitare utenti anonimi**.

5.  Fare clic su **Commit**.

6.  Sulla barra di spostamento sinistra fare clic su **Utenti** e quindi cercare l'account utente che si desidera configurare.

7.  Nella tabella dei risultati di ricerca fare clic sull'account utente, fare clic su **Modifica** e quindi fare clic su **Mostra dettagli**.

8.  In **Modifica utente di Skype for Business Server** in Criteri conferenza selezionare il criterio utente con la configurazione di accesso utente anonimo che si desidera applicare all'utente.   

    > [!NOTE]  
    > Le <STRONG> &lt; impostazioni automatiche &gt; </STRONG> applicano le impostazioni di installazione predefinite del server e vengono applicate automaticamente dal server.


Per consentire agli utenti di invitare utenti anonimi alle conferenze, è inoltre necessario abilitare il supporto per gli utenti anonimi nell'organizzazione. Per informazioni dettagliate, vedere [Configurare i criteri per controllare l'accesso degli utenti pubblici in Skype for Business Server.](../external-access-policies/configure-policies-to-control-public-user-access.md)

