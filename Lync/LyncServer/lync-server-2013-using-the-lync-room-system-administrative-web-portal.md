---
title: 'Lync Server 2013: utilizzo del portale Web amministrativo di Lync room System'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Room System Administrative Web Portal
ms:assetid: c387b2a3-3e42-4642-af72-88126ed2820f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743660(v=OCS.15)
ms:contentKeyID: 62268951
ms.date: 11/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 677fdd070994c8cc1f63f775ffb2569642768f0e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529943"
---
# <a name="using-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a>Utilizzo del portale Web amministrativo di Lync room System in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-11-10_

Dopo la distribuzione di LRS nel server, è possibile controllare lo stato di tutte le sale di LRS accedendo al portale di amministrazione di LRS da un browser.

<div>

## <a name="sign-in"></a>Accesso

1.  Passare all'URL seguente:
    
    https:// \<fe-server\> /LRS

2.  Immettere le credenziali per l'account di LRSSupport o un account che è stato aggiunto al gruppo di sicurezza di LRSSupportAdminGroup.

![Schermata di accesso al portale di amministrazione di Lync room System](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Schermata di accesso al portale di amministrazione di Lync room System")

</div>

<div>

## <a name="lrs-administrative-web-portal-summary-page"></a>Pagina di riepilogo del portale Web amministrativo di LRS

Nella pagina Riepilogo sono disponibili le informazioni seguenti per tutte le sale di LRS distribuite nel server:

  - **Tag**     Nome personalizzato che viene fornito dall'amministratore per la sala. Il tag può essere impostato nel portale facendo clic sul nome della sala.

  - **Integrità**     Lo stato di integrità della sala, che deriva dallo stato di integrità di aggregazione della sala, visualizzata nella sezione integrità della pagina impostazioni sala.

  - **Prossima riunione**     Data e ora in cui viene pianificata la riunione successiva.

  - **Versione di LRS, produttore, modello**     Questi valori sono preimpostati in LRS. A seconda del produttore, questi campi potrebbero essere lasciati vuoti.

  - **Ultimo aggiornamento**     Visualizza l'ultima volta che la pagina Web è stata aggiornata.

![Visualizzazione di riepilogo del portale di amministrazione di Lync room System](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Visualizzazione di riepilogo del portale di amministrazione di Lync room System")

</div>

<div>

## <a name="lrs-room-information"></a>Informazioni sulla sala LRS

La sezione informazioni sala del portale consente di visualizzare e configurare le singole sale di LRS. Contiene quattro sezioni: impostazioni, dettagli, risoluzione dei problemi e integrità.

<div>

## <a name="settings"></a>Impostazioni

Nella sezione impostazioni è possibile impostare la password, il tag sala e i livelli di volume predefiniti per la sala. Se si configurano queste impostazioni, le modifiche vengono replicate solo dopo aver riavviato la console di LRS. Verranno visualizzate solo le impostazioni degli aggiornamenti di sistema per i sistemi sala Lync che sono la versione 15,12 e versioni successive.

![Impostazioni delle sale del portale di amministrazione di Lync room System](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Impostazioni delle sale del portale di amministrazione di Lync room System")

</div>

<div>

## <a name="details"></a>Dettagli

Nella sezione dettagli viene fornito un riepilogo di sola lettura delle impostazioni della sala LRS, tra cui: l'ora dell'ultimo aggiornamento. prossima riunione; ultimi aggiornamenti, manutenzione e calibrazione; impostazioni predefinite per altoparlanti, MIC e suonerie; versione URI SIP; numero di schermate e dettagli relativi a ogni schermata; stato e attività.

![Visualizzazione dettagli del portale di amministrazione di Lync room System](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Visualizzazione dettagli del portale di amministrazione di Lync room System")

</div>

<div>

## <a name="troubleshooting"></a>Risoluzione dei problemi

La sezione risoluzione dei problemi può essere utilizzata per raccogliere i log in remoto e salvarli in una posizione specificata. È inoltre possibile riavviare la console di LRS (interfaccia utente di LRS) o riavviare l'intero sistema. Per raccogliere i registri, specificare un percorso di cartella nel formato specificato e verificare che la cartella disponga delle autorizzazioni di scrittura concesse all'account del computer LRS. Se la dimensione del registro è troppo grande, è possibile richiedere fino a 5 minuti per completare la raccolta dei registri. L'aggiornamento della pagina consente di ottenere lo stato più recente.

![Registrazione sala del portale di amministrazione di Lync room System](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Registrazione sala del portale di amministrazione di Lync room System")

</div>

<div>

## <a name="health"></a>Sanità

La sezione Health fornisce un'indicazione visiva dell'integrità della connessione di Lync Server, del dispositivo audio, del dispositivo video, dello stato di resilienza e del dispositivo schermo.

![Integrità della sala del portale di amministrazione di Lync room System](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Integrità della sala del portale di amministrazione di Lync room System")

</div>

</div>

<div>

## <a name="additional-notes-about-the-administrative-web-portal"></a>Note aggiuntive sul portale Web amministrativo

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>Le modifiche apportate alle impostazioni vengono applicate solo dopo il riavvio del sistema LRS.</P>
> <LI>
> <P>Se la password dell'account LRSApp scade, l'utente non sarà in grado di visualizzare lo stato delle chat room. Configurare la password dell'account LRSAppuser in modo che non scada mai o accertarsi di aggiornare la password al termine della scadenza.</P>
> <LI>
> <P>Il portale Web amministrativo di LRS è supportato solo per le distribuzioni locali.</P></LI></UL>



</div>

</div>

<div>

## <a name="frequently-asked-questions"></a>Domande frequenti

<div>

## <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>Perché non è possibile accedere al portale Web amministrativo?

  - Quando si apre https://localhost/lrs , si sarà in grado di visualizzare la pagina di accesso, ma quando si digita le credenziali, non è possibile accedere. In questo caso, è necessario aprire https://FQDNofFEserver/lrs per accedere al portale Web amministrativo.

  - Se il computer da cui si sta accedendo al portale Web amministrativo è in un gruppo di lavoro, "http://" non funzionerà. Utilizzare invece "https".

</div>

<div>

## <a name="why-cant-i-see-lrs-in-the-administrative-web-portal"></a>Perché non è possibile visualizzare LRS nel portale Web amministrativo?

  - Verificare di disporre degli account di LRS nella distribuzione e che vengano creati in base ai suggerimenti relativi alla distribuzione del portale Web amministrativo di LRS. Verificare che gli account di LRS siano sottoposto a provisioning mediante Enable-CsMeetingRoom, not Enable-CsUser, sul server Lync.

  - Se sono stati creati account di LRS e non è possibile visualizzare gli account nel portale Web amministrativo, raccogliere i registri del server utilizzando lo strumento di registrazione di Lync Server con il componente **MeetingPortal** selezionato e quindi inviarli al contatto di supporto di LRS.

</div>

<div>

## <a name="why-cant-i-see-the-status-of-lrs-in-the-administrative-web-portal"></a>Perché non è possibile visualizzare lo stato di LRS nel portale Web di amministrazione?

  - Verificare che l'account utente di LRSApp sia abilitato per SIP.

  - Se si verificano ancora problemi, raccogliere il file **Trace. log** nel sistema LRS da D: \\ Tracing \\ LRSAdminLogs \\ e quindi inviarlo al contatto di supporto di LRS.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

