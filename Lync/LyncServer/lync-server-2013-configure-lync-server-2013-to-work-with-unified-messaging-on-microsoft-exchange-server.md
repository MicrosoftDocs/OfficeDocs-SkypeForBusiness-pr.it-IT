---
title: "Lync Server 2013: Configurare Lync Server 2013 per l'utilizzo della messaggistica unificata in Microsoft Exchange Server"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server
ms:assetid: 1098ae4d-f57f-44f3-804e-39889d9fc14e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398193(v=OCS.15)
ms:contentKeyID: 48183430
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27909f4ae6231b1452cbfefdd82e0a0eb107c6fa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985481"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server"></a>Configurare Lync Server 2013 per l'utilizzo della messaggistica unificata in Microsoft Exchange Server

</div>

<div id="mainSection">

<div id="mainBody">

_**Argomento Ultima modifica:** 2013-04-03_

Questo passaggio richiede l'utilità di integrazione della messaggistica unificata di Exchange (OcsUmUtil. exe). Questo strumento si trova nel server Lync Server 2013 nel.. \\Programmi file\\comuni cartella\\di supporto di Microsoft\\Lync Server 2013.

<div>

## <a name="running-the-exchange-um-integration-utility"></a>Eseguire l'utilità di integrazione della messaggistica unificata di Exchange

L'utilità di integrazione della messaggistica unificata di Exchange deve essere eseguita da un account utente con le caratteristiche seguenti:

  - Appartenenza ai gruppi RTCUniversalServerAdmins e RtcUniversalUserAdmins, che includono le autorizzazioni per la lettura delle impostazioni di messaggistica unificata di Exchange Server.

  - Diritti utente nel dominio per creare oggetti contatto nel contenitore dell'unità organizzativa specificata.

Quando si esegue l'utilità di integrazione della messaggistica unificata di Exchange, vengono eseguite le attività seguenti:

  - Crea oggetti contatto per ogni numero di accesso automatico e Sottoscrittore che deve essere usato dagli utenti di VoIP aziendale.

  - Verifica che il nome di ogni piano di chiamata VoIP aziendale corrisponda al contesto telefonico di dial plan di messaggistica unificata corrispondente. Questa corrispondenza è necessaria solo se il dial plan di messaggistica unificata viene eseguito in una versione di Exchange *precedente* rispetto a Exchange 2010 Service Pack 1 (SP1).

> [!IMPORTANT]
> Prima di eseguire l'utilità di integrazione della messaggistica unificata di Exchange, verificare di aver eseguito le operazioni seguenti:
> <ul>
> <li><p>Creare uno o più dial plan di messaggistica unificata di Exchange, come descritto nella documentazione del prodotto Exchange.</p>
> <p>Per Microsoft Exchange Server 2010, vedere &quot;creare un dial plan&quot; di <a href="http://go.microsoft.com/fwlink/p/?linkid=186177">http://go.microsoft.com/fwlink/p/?linkId=186177</a>messaggistica unificata.</p>
> <p>Per Microsoft Exchange Server 2007 Service Pack 1 (SP1), vedere &quot;come creare un dial plan&quot; URI SIP di messaggistica unificata. <a href="http://go.microsoft.com/fwlink/p/?linkid=185771">http://go.microsoft.com/fwlink/p/?linkId=185771</a></p></li>
> <li><p>Creare uno o più piani di chiamata di Lync Server corrispondenti, come descritto in <a href="lync-server-2013-create-a-dial-plan.md">creare un dial plan in Lync server 2013</a>.</p></li>
> <ul><li>Se si usa una versione di Exchange precedente a Microsoft Exchange Server 2010 SP1, è necessario immettere il nome di dominio completo (FQDN) del relativo dial plan di messaggistica unificata di Exchange nel campo <STRONG>nome semplice</STRONG> di Lync Server 2013 dial plan. Se si usa Microsoft Exchange Server 2010 SP1 o il Service Pack più recente, non è necessario questo nome per il dial plan.</li></ul>
> <li>Creare un operatore automatico e verificare che il numero di accesso del Sottoscrittore e il numero di operatore automatico siano in formato E. 164.</li></ul>


<div>

## <a name="to-run-the-exchange-um-integration-utility"></a>Per eseguire l'utilità di integrazione della messaggistica unificata di Exchange

1.  In un server front-end aprire un prompt dei comandi e digitare **CD% COMMONPROGRAMFILES\\% Microsoft Lync Server\\2013 support**e quindi premere INVIO.

2.  Digitare **OcsUmUtil. exe**e quindi premere INVIO.

3.  Fare clic su **Carica dati** per trovare tutte le foreste di Exchange attendibili.

4.  Nell'elenco **dial plan SIP** selezionare un dial plan di messaggistica unificata per cui si vogliono creare oggetti contatto e quindi fare clic su **Aggiungi**.

5.  Nella casella **contatto** accettare l'unità organizzativa predefinita oppure fare clic su **Sfoglia** per avviare la **selezione unità organizzativa**. Nella casella **selezione unità** organizzativa è possibile selezionare un'unità organizzativa e fare clic su **OK**oppure fare clic su **Crea nuova UO** per creare una nuova unità organizzativa nella radice o in qualsiasi altra UO del dominio, ad esempio "ou = account speciali RTC, DC = fourthcoffee, DC = com", e quindi fare clic su **OK**.
    
    <div>
    

    > [!NOTE]  
    > Il nome distinto (DN) dell'unità organizzativa selezionata o creata viene ora visualizzato nella casella <STRONG>unità organizzativa</STRONG> .

    
    </div>

6.  Nella casella **nome** accettare il nome predefinito del dial plan o digitare un nuovo nome visualizzato per l'oggetto contatto che si sta creando.
    
    <div>
    

    > [!NOTE]  
    > Ad esempio, se stai creando un oggetto contatto di accesso sottoscrittore, potresti semplicemente denominarlo accesso sottoscrittore.

    
    </div>

7.  Nella casella **indirizzo SIP** accettare l'indirizzo SIP predefinito oppure digitare un nuovo indirizzo SIP.
    
    <div>
    

    > [!NOTE]  
    > Se si digita un nuovo indirizzo SIP, è necessario che inizi con <STRONG>SIP:</STRONG> ovvero "SIP:", inclusi i due punti.

    
    </div>

8.  Nell'elenco **Server o pool** selezionare il server Standard Edition o il pool Front end in cui deve essere abilitato l'oggetto contatto.
    
    <div>
    

    > [!NOTE]  
    > Preferibilmente, il pool selezionato è lo stesso pool in cui sono distribuiti gli utenti abilitati per la messaggistica unificata di Exchange e Enterprise Voice.

    
    </div>

9.  Nell'elenco **numero di telefono** selezionare **Immetti numero di telefono** o **usare questo numero pilota dalla messaggistica unificata di Exchange** e quindi immettere un numero di telefono.

10. Nell'elenco **tipo di contatto** selezionare il tipo di contatto che si vuole creare e quindi fare clic su **OK**.

11. Ripetere i passaggi da 1 a 10 per gli oggetti contatto aggiuntivi che si desidera creare.
    
    <div>
    

    > [!NOTE]  
    > Devi creare almeno un contatto per ogni operatore automatico. Se si vuole l'accesso esterno, è necessario anche un contatto di accesso abbonato e specificare i numeri di chiamata diretta.

    
    </div>

</div>

Per verificare che gli oggetti contatto siano stati creati, aprire utenti e computer di Active Directory e selezionare l'unità organizzativa in cui sono stati creati gli oggetti. Gli oggetti contatto devono essere visualizzati nel riquadro dei dettagli.

</div>

</div>

<span> </span>

</div>

</div>

</div>

