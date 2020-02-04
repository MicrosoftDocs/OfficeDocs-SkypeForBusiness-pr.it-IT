---
title: 'Lync Server 2013: Uso del portale Web amministrativo di Lync Room System'
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
ms.openlocfilehash: c891309d76dda20f875592841925c852fe2e3351
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743936"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a>Uso del portale Web amministrativo di Lync Room System in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-11-10_

Dopo la distribuzione di LRS nel server, è possibile controllare lo stato di tutte le sale di LRS accedendo al portale Web amministrativo di LRS da un browser.

<div>

## <a name="sign-in"></a>Accedi

1.  Passare all'URL seguente:
    
    https://\<Fe-server\>/LRS

2.  Immettere le credenziali per l'account di LRSSupport o un account aggiunto al gruppo di sicurezza di LRSSupportAdminGroup.

![Schermata di accesso al portale di amministrazione di Lync Room System](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Schermata di accesso al portale di amministrazione di Lync Room System")

</div>

<div>

## <a name="lrs-administrative-web-portal-summary-page"></a>Pagina di riepilogo di LRS Administrative Web Portal

Nella pagina di riepilogo sono disponibili le informazioni seguenti per tutte le sale LRS distribuite nel server:

  - **Contrassegnare**   il nome personalizzato che l'amministratore assegna alla chat room. Il tag può essere impostato nel portale facendo clic sul nome della chat room.

  - **Integrità**   lo stato di integrità della sala, derivato dallo stato di integrità aggregato della sala, visualizzato nella sezione integrità della pagina impostazioni sala.

  - **Riunione successiva la**   data e l'ora in cui è programmata la riunione successiva.

  - **LRS versione, produttore, modello**   questi valori sono preimpostati in LRS. A seconda del produttore, questi campi potrebbero essere lasciati vuoti.

  - **L'ultimo aggiornamento**   Visualizza l'ultima volta che è stata aggiornata la pagina Web.

![Visualizzazione di riepilogo del portale di amministrazione di Lync Room System](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Visualizzazione di riepilogo del portale di amministrazione di Lync Room System")

</div>

<div>

## <a name="lrs-room-information"></a>LRS informazioni sulle camere

La sezione informazioni sala del portale consente di visualizzare e configurare singole sale LRS. Contiene quattro sezioni: impostazioni, dettagli, risoluzione dei problemi e integrità.

<div>

## <a name="settings"></a>Impostazioni

Nella sezione Impostazioni puoi impostare la password, il tag room e i livelli di volume predefiniti per la chat room. Se si configurano queste impostazioni, le modifiche verranno replicate solo dopo aver riavviato la console LRS. Verranno visualizzate solo le impostazioni di aggiornamenti di sistema per i sistemi room Lync versione 15,12 e successive.

![Impostazioni della sala nel portale di amministrazione di Lync Room System](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Impostazioni della sala nel portale di amministrazione di Lync Room System")

</div>

<div>

## <a name="details"></a>Dettagli

La sezione dettagli offre un riepilogo di sola lettura delle impostazioni della sala LRS, tra cui: l'ora dell'ultimo aggiornamento; riunione successiva; ultimi aggiornamenti, manutenzione e calibrazione; impostazioni predefinite altoparlante, microfono e suoneria; versione URI SIP; numero di schermate e dettagli su ogni schermata; stato e attività.

![Visualizzazione dettagliata del portale di amministrazione di Lync Room System](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Visualizzazione dettagliata del portale di amministrazione di Lync Room System")

</div>

<div>

## <a name="troubleshooting"></a>Risoluzione dei problemi

La sezione risoluzione dei problemi può essere usata per raccogliere i log in remoto e salvarli in una posizione specifica. È anche possibile riavviare la console LRS (interfaccia utente di LRS) o riavviare l'intero sistema. Per raccogliere i log, specificare un percorso di cartella nel formato specificato e verificare che la cartella disponga delle autorizzazioni di scrittura assegnate all'account del computer LRS. Se le dimensioni del log sono troppo grandi, possono essere necessarie fino a 5 minuti per completare la raccolta dei log. L'aggiornamento della pagina ti darà lo stato più recente.

![Registrazione della sala nel portale di amministrazione di Lync Room System](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Registrazione della sala nel portale di amministrazione di Lync Room System")

</div>

<div>

## <a name="health"></a>Integrità

La sezione integrità offre un'indicazione visiva dell'integrità della connessione Lync Server, del dispositivo audio, del dispositivo video, dello stato di resilienza e del dispositivo schermo.

![Integrità della sala nel portale di amministrazione di Lync Room System](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Integrità della sala nel portale di amministrazione di Lync Room System")

</div>

</div>

<div>

## <a name="additional-notes-about-the-administrative-web-portal"></a>Altre note sul portale Web amministrativo

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>L'impostazione delle modifiche viene applicata solo dopo il riavvio del sistema LRS.</P>
> <LI>
> <P>Se la password dell'account LRSApp scade, non sarà possibile visualizzare lo stato delle chat room. Configurare la password dell'account di LRSAppuser in modo che non scada mai o assicurarsi di aggiornare la password quando è vicina alla scadenza.</P>
> <LI>
> <P>Il portale Web amministrativo di LRS è supportato solo per le distribuzioni locali.</P></LI></UL>



</div>

</div>

<div>

## <a name="frequently-asked-questions"></a>Domande frequenti

<div>

## <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>Perché non è possibile accedere al portale Web amministrativo?

  - Quando si apre https://localhost/lrs, sarà possibile visualizzare la pagina di accesso, ma quando si digita le credenziali non è possibile accedere. In questo caso, è necessario aprire https://FQDNofFEserver/lrs per accedere al portale Web amministrativo.

  - Se il computer da cui si accede al portale Web amministrativo è in un gruppo di lavoro, "http://" non funzionerà. USA invece "https".

</div>

<div>

## <a name="why-cant-i-see-lrs-in-the-administrative-web-portal"></a>Perché non è possibile visualizzare LRS nel portale Web amministrativo?

  - Verificare di avere gli account di LRS nella distribuzione e di essere creati in base ai consigli di distribuzione di LRS Administrative Web Portal. Verificare che gli account di LRS vengano provisionati usando Enable-CsMeetingRoom, non Enable-CsUser, nel server Lync.

  - Se sono stati creati account di LRS e non è possibile visualizzare gli account nel portale Web amministrativo, raccogliere i log del server usando lo strumento di registrazione di Lync Server con il componente **MeetingPortal** selezionato e quindi inviarli al contatto di supporto di LRS.

</div>

<div>

## <a name="why-cant-i-see-the-status-of-lrs-in-the-administrative-web-portal"></a>Perché non è possibile visualizzare lo stato di LRS nel portale Web amministrativo?

  - Verificare che l'account utente di LRSApp sia abilitato per SIP.

  - Se si verificano ancora problemi, raccogliere il file **Trace. log** nel sistema LRS da D:\\Tracing\\LRSAdminLogs\\e quindi inviarlo al contatto di supporto di LRS.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

