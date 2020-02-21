---
title: 'Lync Server 2013: applicazione di un criterio di archiviazione di Lync Server a un utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Applying a Lync Server Archiving policy to a user
ms:assetid: a23e4876-aa8d-4f49-a3bd-3696616e8290
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205143(v=OCS.15)
ms:contentKeyID: 48185024
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1cc8659035e6df437d10684eb1bd0158a76b7a0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="applying-a-lync-server-archiving-policy-to-a-user-in-lync-server-2013"></a>Applicazione di un criterio di archiviazione di Lync Server a un utente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-10_

Dopo aver creato un criterio utente di Lync Server, è necessario applicarlo a specifici utenti o gruppi utente ospitati in Lync Server 2013 prima che possa essere applicato. Per informazioni dettagliate sulla creazione di criteri utente per utenti specifici, vedere [Creating and Configuring User Policies for archiving in Lync Server 2013](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md) nella documentazione relativa alla distribuzione.

Per informazioni dettagliate sul funzionamento dei criteri di archiviazione, inclusa la gerarchia per i criteri globali, sito e utente, vedere [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) nella documentazione relativa alla pianificazione, alla distribuzione o alla documentazione relativa alle operazioni.

<div>


> [!NOTE]  
> Per configurare e utilizzare l'archiviazione, è innanzitutto necessario distribuire l'archiviazione. Per informazioni dettagliate, vedere <A href="lync-server-2013-deploying-archiving.md">Deploying Archiving in Lync Server 2013</A> nella documentazione relativa alla distribuzione.<BR>Se è stata abilitata l'integrazione di Microsoft Exchange per la distribuzione, i criteri di conservazione sul posto di Exchange controllano se l'archiviazione è abilitata per gli utenti ospitati in Exchange 2013 e le relative cassette postali vengono conservate sul posto. Per informazioni dettagliate, vedere <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">impostazione dei criteri per l'archiviazione in Lync server 2013 quando si utilizza l'integrazione di Exchange Server</A> nella documentazione relativa alla distribuzione.<BR>Specificare tutte le opzioni appropriate nelle configurazioni di archiviazione prima di abilitare l'archiviazione. Per ulteriori informazioni, vedere <A href="lync-server-2013-configuring-archiving-options.md">configurazione delle opzioni di archiviazione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.



</div>

<div>

## <a name="to-apply-a-lync-server-archiving-policy-to-a-user"></a>Per applicare un criterio di archiviazione di Lync Server a un utente

1.  Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Lync Server 2013. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server 2013, vedere [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Utenti** e quindi cercare l'account utente che si desidera configurare.

4.  Nella tabella dei risultati di ricerca fare clic sull'account utente, fare clic su **Modifica** e quindi fare clic su **Mostra dettagli**.

5.  In **modifica utente di Lync Server** in **criteri di archiviazione**Selezionare i criteri utente di archiviazione che si desidera applicare.
    
    <div>
    

    > [!NOTE]  
    > Le <STRONG> &lt;impostazioni&gt; automatiche</STRONG> applicano le impostazioni di installazione predefinite del server. Queste impostazioni vengono applicate automaticamente dal server.

    
    </div>

6.  Fare clic su **Commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

