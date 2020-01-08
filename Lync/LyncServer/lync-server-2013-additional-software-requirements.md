---
title: 'Lync Server 2013: Requisiti software aggiuntivi'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Additional software requirements
ms:assetid: 87b318e3-03ae-41f7-af5e-29bb294f6af0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398686(v=OCS.15)
ms:contentKeyID: 48184731
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e21a375fecbd109e108806dc816a9fa3fce81a2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976627"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="additional-software-requirements-for-lync-server-2013"></a>Requisiti software aggiuntivi per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2016-12-08_

Oltre ai requisiti relativi a hardware e sistemi operativi per le piattaforme server, Lync Server 2013 richiede l'installazione di software aggiuntivo nei server distribuiti.

<div>


> [!NOTE]  
> Per informazioni dettagliate sui requisiti della piattaforma per i server che utilizzano Lync Server, vedere <A href="lync-server-2013-server-hardware-platforms.md">piattaforme hardware server per Lync server 2013</A> e supporto per il <A href="lync-server-2013-server-and-tools-operating-system-support.md">sistema operativo per server e strumenti in Lync Server 2013</A>. Per informazioni dettagliate sui requisiti di sistema per i computer e i dispositivi client, vedere <A href="lync-server-2013-planning-for-clients-and-devices.md">pianificazione di client e dispositivi in Lync Server 2013</A> nella documentazione relativa alla pianificazione. Per informazioni dettagliate sui requisiti software per gli strumenti di amministrazione, vedere <A href="lync-server-2013-administrative-tools-software-requirements.md">requisiti software per strumenti di amministrazione in Lync Server 2013</A>.



</div>

<div>

## <a name="additional-software-necessary-for-all-internal-server-roles"></a>Software aggiuntivo necessario per tutti i ruoli server interni

Questa sezione elenca il software necessario per tutti i ruoli server interni, che sono tutti i ruoli di Lync Server server eccetto Edge Server. I requisiti per gli Edge Server e i pool di Edge sono elencati più avanti in questo argomento in **software aggiuntivo per Edge Server**.

</div>

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3,0

Ogni server in cui è in uso Lync Server 2013 deve essere installata la versione corretta di Windows PowerShell 3,0. Per informazioni dettagliate, vedere [installazione di Windows PowerShell 3,0 per Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

</div>

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4,5

Lync Server richiede Microsoft .NET Framework 4,5 in tutti i ruoli server interni e in qualsiasi computer in cui verranno eseguiti gli strumenti di amministrazione di Lync Server o Microsoft Lync Server 2013, strumento di pianificazione. Per Lync Server 2013 è necessario installare manualmente l'edizione a 64 bit di Microsoft .NET Framework 4,5 nel server prima di installare Lync Server 2013. Per installarlo manualmente, scaricare Microsoft .NET 4,5 Framework dall'area download Microsoft all'indirizzo[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)

<div>

## <a name="installing-microsoft-net-framework-45-on-servers-running-windows-server-2012"></a>Installazione di Microsoft .NET Framework 4,5 su server che esegue Windows Server 2012

Quando si installa Microsoft .NET Framework 4,5 su server che eseguono Lync Server 2013 e Windows Server 2012, è necessario eseguire un ulteriore passaggio. Dopo l'installazione di .NET Framework 4,5, usare Server Manager per installare l'attivazione HTTP.

**Per installare l'attivazione HTTP di .NET 4,5 in Windows Server 2012**

1.  Nel menu **Start** fare clic su **programmi**, quindi su **strumenti di amministrazione**e quindi su **Gestione server**.

2.  In Server Manager, in **Riepilogo funzionalità**, scegliere **Aggiungi funzionalità**.

3.  Espandere **.NET Framework 4,5**.

4.  Selezionare l' **attivazione di WCF** se non è già selezionata. Quindi seleziona **attivazione http**.

5.  Fare clic su **Avanti** e seguire le istruzioni per completare l'installazione.

</div>

</div>

<div>

## <a name="windows-identity-foundation"></a>Windows Identity Foundation

**Windows Identity Foundation** in Lync Server 2013 richiede l'installazione di Windows Identity Foundation per supportare gli scenari di autenticazione server-server. Windows Server 2008 R2 e Windows Server 2012 richiedono diverse procedure per installare Windows identifica Foundation. Selezionare il sistema operativo del server dall'elenco seguente:

  - Windows Server 2008 R2 per Windows Server 2008 R2, verificare se è già stato installato nel computer. Per eseguire questa operazione, vedere **aggiungere/rimuovere programmi**, **visualizzare gli aggiornamenti installati**e cercare in **Windows** per la voce **Windows Identity Foundation (KB974405)**. Per informazioni dettagliate sull'installazione di Windows Identity Foundation [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657), vedere.

  - Windows Server 2012 per Windows Server 2012, è possibile usare **Server Manager** per installare Windows Identity Foundation. Nella **procedura guidata per l'aggiunta di ruoli e funzionalità**in Server Manager selezionare **funzionalità**. Selezionare **Windows Identity Foundation 3,5** dall'elenco. Fare clic su **Avanti**e quindi su **Installa**.

</div>

<div>

## <a name="additional-software-for-all-front-end-servers-and-standard-edition-servers"></a>Software aggiuntivo per tutti i server front-end e i server Standard Edition

Tutti i server front-end e i server Standard Edition devono eseguire anche Internet Information Services (IIS) con determinati moduli. Inoltre, tutti i server front-end e i server Standard Edition in cui sono distribuiti i servizi di conferenza, l'applicazione di Call Park, l'annuncio o i gruppi di risposta devono eseguire Windows Media Format Runtime.

<div>

## <a name="internet-information-services-iis"></a>Internet Information Services (IIS)

I server front-end e i server Standard Edition devono eseguire Internet Information Services (IIS), con i moduli seguenti:

  - Contenuto statico

  - Documento predefinito

  - Errori HTTP

  - ASP.NET

  - Estensibilità .NET

  - Estensioni ISAPI (Internet Server API)

  - Filtri ISAPI

  - Registrazione HTTP

  - Strumenti di registrazione

  - Traccia

  - Autenticazione di Windows

  - Filtro delle richieste

  - Compressione del contenuto statico

  - Compressione del contenuto dinamico

  - Console di gestione di IIS

  - Script e strumenti di gestione di IIS

  - Autenticazione anonima (questa operazione viene installata per impostazione predefinita quando IIS è installato).

  - Autenticazione del mapping dei certificati client

</div>

<div>

## <a name="windows-media-format-runtime-and-windows-desktop-experience"></a>Windows Media Format Runtime e Windows Desktop Experience

**Esperienza desktop di Windows** Tutti i server front-end e i server Standard Edition in cui verranno distribuiti i servizi di conferenza devono avere installato Windows Media Format Runtime, che, ad eccezione di Windows Server 2012, è installato come parte dell'esperienza desktop di Windows. Windows Server 2012 richiede Microsoft Media Foundation. Windows Media Format Runtime è necessario per eseguire i file di Windows Media Audio (con estensione WMA) che vengono riprodotti dalle applicazioni Park, annuncio e Response Group per gli annunci e la musica.

È consigliabile installare Windows Desktop Experience prima di installare Lync Server 2013. Se Lync Server 2013 non trova il software sul server, verrà richiesto di installarlo e quindi sarà necessario riavviare il server per completare l'installazione.

</div>

</div>

<div>

## <a name="additional-software-for-front-end-servers-and-standard-edition-servers-running-on-windows-server-2012"></a>Software aggiuntivo per i server front-end e i server Standard Edition in Windows Server 2012

I server front-end richiedono .NET 3,5, che non è installato per impostazione predefinita in Windows Server 2012. Per installarlo, inserire il supporto di installazione di Windows Server 2012 nell'unità D e digitare quanto segue:

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

Per informazioni dettagliate sull'installazione di .NET 3,5 nei server che esegue Windows Server 2012, vedere "Considerazioni sulla distribuzione di Microsoft <https://go.microsoft.com/fwlink/p/?linkid=275032>.net Framework 3,5".

</div>

<div>

## <a name="additional-software-for-directors"></a>Software aggiuntivo per amministratori

Gli amministratori devono eseguire Internet Information Services (IIS) con i moduli seguenti:

  - Contenuto statico

  - Documento predefinito

  - Errori HTTP

  - ASP.NET

  - Estensibilità .NET

  - Estensioni ISAPI (Internet Server API)

  - Filtri ISAPI

  - Registrazione HTTP

  - Strumenti di registrazione

  - Traccia

  - Autenticazione di Windows

  - Filtro delle richieste

  - Compressione del contenuto statico

  - Console di gestione di IIS

  - Script e strumenti di gestione di IIS

  - Autenticazione anonima (questa operazione viene installata per impostazione predefinita quando IIS è installato).

  - Autenticazione del mapping dei certificati client

</div>

<div>

## <a name="additional-software-for-persistent-chat-front-end-servers"></a>Software aggiuntivo per i server front end della chat persistente

I server front-end della chat persistente devono eseguire Accodamento messaggi (noto anche come MSMQ), che è un componente di Windows Server.

Per informazioni sull'abilitazione di MSMQ, [fare clic qui.](https://technet.microsoft.com/en-us/library/cc771474.aspx)

</div>

<div>

## <a name="additional-software-for-edge-servers"></a>Software aggiuntivo per Edge Server

I server perimetrali richiedono il software seguente:

  - Ogni server in cui è in uso Lync Server 2013 deve essere installata la versione corretta di Windows PowerShell 3,0. Per informazioni dettagliate, vedere [installazione di Windows PowerShell 3,0 per Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

  - Lync Server richiede Microsoft .NET Framework 4,5. Per Lync Server 2013 installato in Windows Server 2008 R2, è necessario installare manualmente l'edizione a 64 bit di Microsoft .NET Framework 4,5 nel server prima di installare Lync Server 2013. Per installarlo manualmente, scaricare Microsoft .NET 4,5 Framework dall'area download Microsoft all'indirizzo[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)

  - **Windows Identity Foundation** in Lync Server 2013 richiede l'installazione di Windows Identity Foundation per supportare gli scenari di autenticazione server-server. Windows Server 2008 R2 e Windows Server 2012 richiedono diverse procedure per installare Windows identifica Foundation. Selezionare il sistema operativo del server dall'elenco seguente:
    
      - Windows Server 2008 R2 per Windows Server 2008 R2, verificare se è già stato installato nel computer. Per eseguire questa operazione, vedere **aggiungere/rimuovere programmi**, **visualizzare gli aggiornamenti installati**e cercare in **Windows** per la voce **Windows Identity Foundation (KB974405)**. Per informazioni dettagliate sull'installazione di Windows Identity Foundation [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657), vedere.
    
      - Windows Server 2012 per Windows Server 2012, è possibile usare **Server Manager** per installare Windows Identity Foundation. Nella **procedura guidata per l'aggiunta di ruoli e funzionalità**in Server Manager selezionare **funzionalità**. Selezionare **Windows Identity Foundation 3,5** dall'elenco. Fare clic su **Avanti**e quindi su **Installa**.

</div>

<div>

## <a name="do-not-install-layered-socket-providers-on-media-servers"></a>Non installare provider di socket sovrapposti nei server multimediali

Non installare alcun software client server ISA (Microsoft Internet Security and Acceleration) o qualsiasi altro software LSP (Layered Service Provider) Winsock in qualsiasi server front-end o mediazione autonoma. L'installazione di questo software può causare scarse prestazioni del traffico multimediale.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Requisiti software degli strumenti di amministrazione in Lync Server 2013](lync-server-2013-administrative-tools-software-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

