---
title: 'Lync Server 2013: requisiti software aggiuntivi'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Additional software requirements
ms:assetid: 87b318e3-03ae-41f7-af5e-29bb294f6af0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398686(v=OCS.15)
ms:contentKeyID: 48184731
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4565f91afeb703de967040edb8f6d437aedac9eb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196399"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="additional-software-requirements-for-lync-server-2013"></a>Requisiti software aggiuntivi per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2016-12-08_

Oltre ai requisiti hardware e del sistema operativo per le piattaforme server, Lync Server 2013 richiede l'installazione di software aggiuntivo nei server distribuiti.

<div>


> [!NOTE]  
> Per informazioni dettagliate sui requisiti della piattaforma per i server che eseguono Lync Server, vedere <A href="lync-server-2013-server-hardware-platforms.md">server hardware Platforms for Lync server 2013</A> and <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and Tools Operating System Support in Lync Server 2013</A>. Per informazioni dettagliate sui requisiti di sistema per i computer e i dispositivi client, vedere <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and Devices in Lync Server 2013</A> nella documentazione relativa alla pianificazione. Per informazioni dettagliate sui requisiti software per gli strumenti di amministrazione, vedere <A href="lync-server-2013-administrative-tools-software-requirements.md">Administrative Tools software requirements in Lync Server 2013</A>.



</div>

<div>

## <a name="additional-software-necessary-for-all-internal-server-roles"></a>Software aggiuntivo necessario per tutti i ruoli del server interni

In questa sezione sono elencati i software necessari per tutti i ruoli del server interni, ovvero tutti i ruoli del server Lync Server, ad eccezione del server perimetrale. I requisiti per i server perimetrali e i pool perimetrali sono elencati più avanti in questo argomento in **software aggiuntivo per i server perimetrali**.

</div>

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

Per ogni server che esegue Lync Server 2013 deve essere installata la versione corretta di Windows PowerShell 3,0. Per ulteriori informazioni, vedere [Installing Windows PowerShell 3,0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

</div>

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4.5

Lync Server richiede Microsoft .NET Framework 4,5 su tutti i ruoli del server interno e su qualsiasi computer in cui verranno eseguiti gli strumenti di amministrazione di Lync Server o Microsoft Lync Server 2013, strumento di pianificazione. Per Lync Server 2013, è necessario installare manualmente l'edizione a 64 bit di Microsoft .NET Framework 4,5 sul server prima di installare Lync Server 2013. Per installarlo manualmente, scaricare Microsoft .NET 4,5 Framework dall'area download Microsoft all'indirizzo[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)

<div>

## <a name="installing-microsoft-net-framework-45-on-servers-running-windows-server-2012"></a>Installazione di Microsoft .NET Framework 4,5 nei server che eseguono Windows Server 2012

Quando si installa Microsoft .NET Framework 4,5 nei server che eseguiranno Lync Server 2013 e Windows Server 2012, è necessario eseguire un ulteriore passaggio. Dopo l'installazione di .NET Framework 4,5, utilizzare Server Manager per installare l'attivazione HTTP.

**Per installare l'attivazione di .NET 4,5 HTTP su Windows Server 2012**

1.  Fare clic sul pulsante **Start** , scegliere **programmi**, quindi **strumenti di amministrazione**e quindi fare clic su **Server Manager**.

2.  In Server Manager, in **Riepilogo funzionalità**, scegliere **Aggiungi funzionalità**.

3.  Espandere **.NET Framework 4,5**.

4.  Selezionare **attivazione WCF** se non è già selezionata. Quindi selezionare **attivazione http**.

5.  Fare clic su **Avanti** e seguire le istruzioni per completare l'installazione.

</div>

</div>

<div>

## <a name="windows-identity-foundation"></a>Windows Identity Foundation

**Windows Identity Foundation** in Lync Server 2013 richiede l'installazione di Windows Identity Foundation per supportare gli scenari di autenticazione da server a server. Windows Server 2008 R2 e Windows Server 2012 richiedono procedure diverse per installare Windows identificate Foundation. Selezionare il sistema operativo del server dall'elenco seguente:

  - Windows Server 2008 R2 per Windows Server 2008 R2, controllare se è già stato installato nel computer in uso. A tale scopo, andare a **Aggiungi/Rimuovi programmi**, **visualizzare gli aggiornamenti installati**e cercare in **Windows** per la voce **Windows Identity Foundation (KB974405)**. Per informazioni dettagliate sull'installazione di Windows Identity Foundation [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657), vedere.

  - Windows Server 2012 per Windows Server 2012, è possibile utilizzare **Gestione server** per installare Windows Identity Foundation. Nell' **Aggiunta guidata ruoli e funzionalità**in Server Manager, selezionare **funzionalità**. Selezionare **Windows Identity Foundation 3,5** dall'elenco. Fare clic su **Avanti**e quindi su **Installa**.

</div>

<div>

## <a name="additional-software-for-all-front-end-servers-and-standard-edition-servers"></a>Software aggiuntivo per tutti i Front End Server e i server Standard Edition

Tutti i Front End Server e i server Standard Edition devono eseguire anche Internet Information Services (IIS) con alcuni moduli. Inoltre, tutti i Front End Server e i server Standard Edition in cui vengono distribuite le conferenze, l'applicazione Parcheggio di chiamata, l'annuncio o i Response Group devono eseguire Windows Media Format Runtime.

<div>

## <a name="internet-information-services-iis"></a>Internet Information Services (IIS)

I Front End Server e i server Standard Edition devono eseguire Internet Information Services (IIS), con i moduli seguenti:

  - Contenuto statico

  - Documento predefinito

  - Errori HTTP

  - ASP.NET

  - Estendibilità .NET

  - Estensioni ISAPI (Internet Server API)

  - Filtri ISAPI

  - Registrazione HTTP

  - Strumenti di registrazione

  - Analisi della

  - Autenticazione di Windows

  - Filtro richieste

  - Compressione del contenuto statico

  - Compressione contenuto dinamico

  - Console di gestione IIS

  - Strumenti e script di gestione IIS

  - Autenticazione anonima (è installata per impostazione predefinita durante l'installazione di IIS).

  - Autenticazione mapping certificati client

</div>

<div>

## <a name="windows-media-format-runtime-and-windows-desktop-experience"></a>Windows Media Format Runtime e Windows Desktop Experience

**Esperienza desktop di Windows** Tutti i Front End Server e i server Standard Edition in cui verrà distribuito il servizio di conferenza devono avere installato Windows Media Format Runtime, che, ad eccezione di Windows Server 2012, è installato come parte dell'esperienza desktop di Windows. Windows Server 2012 richiede Microsoft Media Foundation. Runtime formato Windows Media è necessario per l'esecuzione di file Windows Media Audio (con estensione wma) riprodotti dalle applicazioni Parcheggio di chiamata, Annuncio e Response Group per gli annunci e la musica.

È consigliabile installare Windows Desktop Experience prima di installare Lync Server 2013. Se Lync Server 2013 non trova questo software nel server, verrà richiesto di installarlo e quindi sarà necessario riavviare il server per completare l'installazione.

</div>

</div>

<div>

## <a name="additional-software-for-front-end-servers-and-standard-edition-servers-running-on-windows-server-2012"></a>Software aggiuntivo per server front end e server Standard Edition in esecuzione su Windows Server 2012

I Front End Server richiedono .NET 3,5, che non è installato per impostazione predefinita in Windows Server 2012. Per installarlo, inserire il supporto di installazione di Windows Server 2012 nell'unità D e digitare quanto segue:

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

Per informazioni dettagliate sull'installazione di .NET 3,5 nei server che eseguono Windows Server 2012, vedere "Considerazioni sulla distribuzione di Microsoft <https://go.microsoft.com/fwlink/p/?linkid=275032>.net Framework 3,5" all'indirizzo.

</div>

<div>

## <a name="additional-software-for-directors"></a>Software aggiuntivo per i server Director

Gli amministratori devono eseguire Internet Information Services (IIS), con i moduli seguenti:

  - Contenuto statico

  - Documento predefinito

  - Errori HTTP

  - ASP.NET

  - Estendibilità .NET

  - Estensioni ISAPI (Internet Server API)

  - Filtri ISAPI

  - Registrazione HTTP

  - Strumenti di registrazione

  - Analisi della

  - Autenticazione di Windows

  - Filtro richieste

  - Compressione contenuto statico

  - Console di gestione IIS

  - Strumenti e script di gestione IIS

  - Autenticazione anonima (modulo installato per impostazione predefinita durante l'installazione di IIS)

  - Autenticazione mapping certificati client

</div>

<div>

## <a name="additional-software-for-persistent-chat-front-end-servers"></a>Software aggiuntivo per i front end server di chat persistente

I server front end di chat persistente devono eseguire Accodamento messaggi (noto anche come MSMQ), che è un componente di Windows Server.

Per informazioni sull'abilitazione di MSMQ, [fare clic qui.](https://technet.microsoft.com/library/cc771474.aspx)

</div>

<div>

## <a name="additional-software-for-edge-servers"></a>Software aggiuntivo per server perimetrali

I server perimetrali richiedono il software seguente:

  - Per ogni server che esegue Lync Server 2013 deve essere installata la versione corretta di Windows PowerShell 3,0. Per ulteriori informazioni, vedere [Installing Windows PowerShell 3,0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

  - Lync Server richiede Microsoft .NET Framework 4,5. Per Lync Server 2013 installato in Windows Server 2008 R2, è necessario installare manualmente l'edizione a 64 bit di Microsoft .NET Framework 4,5 sul server prima di installare Lync Server 2013. Per installarlo manualmente, scaricare Microsoft .NET 4,5 Framework dall'area download Microsoft all'indirizzo[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)

  - **Windows Identity Foundation** in Lync Server 2013 richiede l'installazione di Windows Identity Foundation per supportare gli scenari di autenticazione da server a server. Windows Server 2008 R2 e Windows Server 2012 richiedono procedure diverse per installare Windows identificate Foundation. Selezionare il sistema operativo del server dall'elenco seguente:
    
      - Windows Server 2008 R2 per Windows Server 2008 R2, controllare se è già stato installato nel computer in uso. A tale scopo, andare a **Aggiungi/Rimuovi programmi**, **visualizzare gli aggiornamenti installati**e cercare in **Windows** per la voce **Windows Identity Foundation (KB974405)**. Per informazioni dettagliate sull'installazione di Windows Identity Foundation [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657), vedere.
    
      - Windows Server 2012 per Windows Server 2012, è possibile utilizzare **Gestione server** per installare Windows Identity Foundation. Nell' **Aggiunta guidata ruoli e funzionalità**in Server Manager, selezionare **funzionalità**. Selezionare **Windows Identity Foundation 3,5** dall'elenco. Fare clic su **Avanti**e quindi su **Installa**.

</div>

<div>

## <a name="do-not-install-layered-socket-providers-on-media-servers"></a>Non installare provider LSP (Layered Service Provider) nei server multimediali

Non installare alcun software client del server Microsoft Internet Security and Acceleration (ISA) o qualsiasi altro software LSP (Layered Service Providers) di Winsock, in tutti i Front End Server o Mediation Server autonomi. L'installazione di questo software potrebbe causare scarse prestazioni del traffico multimediale.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Requisiti software per gli strumenti di amministrazione in Lync Server 2013](lync-server-2013-administrative-tools-software-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

