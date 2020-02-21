---
title: "Lync Server 2013: configurare Lync Server 2013 per l'utilizzo della messaggistica unificata in Microsoft Exchange Server"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server
ms:assetid: 1098ae4d-f57f-44f3-804e-39889d9fc14e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398193(v=OCS.15)
ms:contentKeyID: 48183430
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0dc8bc60f87b981a18f351df8ddd163d1b080be
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197699"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server"></a>Configurare Lync Server 2013 per l'utilizzo della messaggistica unificata in Microsoft Exchange Server

</div>

<div id="mainSection">

<div id="mainBody">

_**Ultimo argomento modificato:** 2013-04-03_

Per questo passaggio è necessaria l'utilità di integrazione della messaggistica unificata di Exchange (OcsUmUtil.exe). Questo strumento si trova sul server Lync Server 2013 nel.. \\Programmi file\\comuni cartella\\di supporto di Microsoft\\Lync Server 2013.

<div>

## <a name="running-the-exchange-um-integration-utility"></a>Esecuzione dell'utilità di integrazione della messaggistica unificata di Exchange

L'utilità di integrazione della messaggistica unificata di Exchange deve essere eseguita con un account utente dotato delle caratteristiche seguenti:

  - Membro dei gruppi RTCUniversalServerAdmins e RtcUniversalUserAdmins (è inclusa l'autorizzazione per la lettura delle impostazioni di messaggistica unificata di Exchange Server)

  - Diritti utente all'interno del dominio per creare oggetti contatto nel contenitore dell'unità organizzativa specificata.

L'utilità di integrazione della messaggistica unificata di Exchange consente di eseguire le attività seguenti:

  - Creazione di oggetti contatto per ogni numero di operatore automatico e di accesso del sottoscrittore che gli utenti di VoIP aziendale devono utilizzare.

  - Verifica che il nome di ogni dial plan VoIP aziendale corrisponda al contesto telefonico del dial plan di messaggistica unificata corrispondente. Questa corrispondenza è necessaria solo se il dial plan di messaggistica unificata è in esecuzione su una versione di Exchange *precedente* a Exchange 2010 Service Pack 1 (SP1).

> [!IMPORTANT]
> Prima di eseguire l'utilità di integrazione della messaggistica unificata di Exchange, accertarsi di aver eseguito le operazioni seguenti:
> <ul>
> <li><p>Creare uno o più dial plan di messaggistica unificata di Exchange, come descritto nella documentazione del prodotto Exchange.</p>
> <p>Per Microsoft Exchange Server 2010, vedere &quot;creare un dial plan&quot; di messaggistica <a href="https://go.microsoft.com/fwlink/p/?linkid=186177">https://go.microsoft.com/fwlink/p/?linkId=186177</a>unificata in.</p>
> <p>Per Microsoft Exchange Server 2007 Service Pack 1 (SP1), vedere &quot;come creare un dial plan&quot; URI SIP di messaggistica unificata in <a href="https://go.microsoft.com/fwlink/p/?linkid=185771">https://go.microsoft.com/fwlink/p/?linkId=185771</a>.</p></li>
> <li><p>Creare uno o più dial plan di Lync Server corrispondenti, come descritto in <a href="lync-server-2013-create-a-dial-plan.md">creare un piano di chiamata in Lync server 2013</a>.</p></li>
> <ul><li>Se si utilizza una versione di Exchange precedente a Microsoft Exchange Server 2010 SP1, è necessario immettere il nome di dominio completo (FQDN) del corrispondente dial plan SIP di messaggistica unificata di Exchange nel campo Lync Server 2013 dial plan <STRONG>Simple Name</STRONG> . Se si utilizza Microsoft Exchange Server 2010 SP1 o Service Pack più recente, il nome del dial plan corrispondente non è necessario.</li></ul>
> <li>Creare un operatore automatico e verificare che il numero di accesso del sottoscrittore e il numero dell'operatore automatico siano nel formato E.164.</li></ul>


<div>

## <a name="to-run-the-exchange-um-integration-utility"></a>Per eseguire l'utilità di integrazione della messaggistica unificata di Exchange

1.  In un front end server, aprire un prompt di comandi e digitare **CD% COMMONPROGRAMFILES\\% Microsoft Lync Server\\2013 support**e quindi premere INVIO.

2.  Digitare **OcsUmUtil.exe** e quindi premere INVIO.

3.  Fare clic su **Carica dati** per trovare tutte le foreste trusted di Exchange.

4.  Nell'elenco **Dial plan SIP** selezionare un dial plan SIP di messaggistica unificata per cui creare gli oggetti contatto, quindi fare clic su **Aggiungi**.

5.  Nella casella **Contatto** accettare l'unità organizzativa predefinita oppure fare clic su **Sfoglia** per avviare **Selezione unità organizzativa**. Nella casella **Selezione unità organizzativa** è possibile selezionare un'unità organizzativa e fare clic su **OK** oppure è possibile fare clic su **Crea nuova unità organizzativa** per creare una nuova unità organizzativa nella radice o in qualsiasi altra unità organizzativa del dominio, ad esempio OU=Account speciali RTC,DC=fourthcoffee,DC=com", e quindi fare clic su **OK**.
    
    <div>
    

    > [!NOTE]  
    > Il nome distinto dell'unità organizzativa selezionata o creata verrà visualizzato nella casella <STRONG>Unità organizzativa</STRONG>.

    
    </div>

6.  Nella casella **Nome** accettare il nome predefinito del dial plan o digitare un nuovo nome visualizzato per l'oggetto contatto che si sta creando.
    
    <div>
    

    > [!NOTE]  
    > Se ad esempio si sta creando un oggetto contatto accesso sottoscrittore, è possibile denominarlo semplicemente Accesso sottoscrittore.

    
    </div>

7.  Nella casella **Indirizzo SIP** accettare l'indirizzo SIP predefinito o digitarne uno nuovo.
    
    <div>
    

    > [!NOTE]  
    > Se si digita un nuovo indirizzo SIP, tale indirizzo deve iniziare con <STRONG>SIP:</STRONG>, ovvero "SIP:" comprensivo dei due punti.

    
    </div>

8.  Nell'elenco **Server o pool** selezionare il server Standard Edition o il pool Front end in cui deve essere abilitato l'oggetto contatto.
    
    <div>
    

    > [!NOTE]  
    > Il pool selezionato preferibilmente deve coincidere con quello in cui sono distribuiti gli utenti abilitati per VoIP aziendale e la messaggistica unificata di Exchange.

    
    </div>

9.  Nell'elenco **Numero di telefono** selezionare **Specifica numero di telefono** o **Usa questo numero pilota dalla messaggistica unificata di Exchange**, quindi immettere un numero di telefono.

10. Nell'elenco **Tipo di contatto** selezionare il tipo di contatto che si desidera creare e quindi fare clic su **OK**.

11. Ripetere i passaggi da 1 a 10 per gli ulteriori oggetti contatto da creare.
    
    <div>
    

    > [!NOTE]  
    > È consigliabile creare almeno un contatto per ogni operatore automatico. Se si desidera disporre dell'accesso esterno, è inoltre necessario un contatto Accesso sottoscrittore e specificare numeri DID (Direct Inward Dial).

    
    </div>

</div>

Per verificare che gli oggetti contatto siano stati creati correttamente, aprire Utenti e computer di Active Directory e selezionare l'unità organizzativa in cui sono stati creati gli oggetti. Gli oggetti contatto dovrebbero essere visualizzati nel riquadro dei dettagli.

</div>

</div>

<span> </span>

</div>

</div>

</div>

