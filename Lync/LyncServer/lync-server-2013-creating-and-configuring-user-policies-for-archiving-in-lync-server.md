---
title: Creazione e configurazione dei criteri utente per l'archiviazione in Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating and configuring user policies for Archiving in Lync Server
ms:assetid: 5af0e605-3563-4d6f-a3c6-511d204a3165
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204923(v=OCS.15)
ms:contentKeyID: 48184234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c40425957d472da2d31d91472634f268dde5b8c5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504673"
---
# <a name="creating-and-configuring-user-policies-for-archiving-in-lync-server-2013"></a>Creazione e configurazione dei criteri utente per l'archiviazione in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-09_

Per abilitare o disabilitare l'archiviazione per utenti specifici ospitati in Lync Server, è necessario innanzitutto creare un criterio utente e quindi applicare il criterio a uno o più utenti o gruppi di utente. Per informazioni dettagliate sull'applicazione di criteri utente a determinati utenti e gruppi di utenti, vedere [applicazione di un criterio di archiviazione di Lync Server a un utente in Lync server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) nella documentazione relativa alla distribuzione.

Per informazioni dettagliate sul funzionamento dei criteri di archiviazione, inclusa la gerarchia per i criteri globali, sito e utente, vedere [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) nella documentazione relativa alla pianificazione, nella documentazione relativa alla distribuzione o nella documentazione relativa alle operazioni.

<div>


> [!NOTE]
> Se è stata abilitata l'integrazione di Microsoft Exchange per la distribuzione, i criteri di Exchange In-Place conservazione determinano se l'archiviazione è abilitata per gli utenti ospitati in Exchange 2013 e le relative cassette postali vengono inserite In-Place blocco. Per informazioni dettagliate, vedere <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">impostazione dei criteri per l'archiviazione in Lync server 2013 quando si utilizza l'integrazione di Exchange Server</A> nella documentazione relativa alla distribuzione.<BR>Specificare tutte le opzioni appropriate nelle configurazioni di archiviazione prima di abilitare l'archiviazione. Per ulteriori informazioni, vedere <A href="lync-server-2013-configuring-archiving-options.md">configurazione delle opzioni di archiviazione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.



</div>

<div>

## <a name="to-configure-an-archiving-policy-for-users-homed-on-lync-server"></a>Per configurare un criterio di archiviazione per gli utenti ospitati in Lync Server

1.  Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Lync Server 2013. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server 2013, vedere [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **Monitoraggio e archiviazione** e quindi su **Criteri di archiviazione**.

4.  Fare clic su **Nuovo** e quindi su **Criteri utente**.

5.  In **Nuovi criteri di archiviazione** eseguire le operazioni seguenti:
    
      - In **Nome** specificare un nome per i criteri utente.
    
      - In **Descrizione** immettere informazioni sugli scopi dei criteri utente, ad esempio "Criteri utente per il reparto legale".
    
      - Per controllare l'archiviazione delle comunicazioni interne per i criteri utente, selezionare o deselezionare la casella di controllo **Archivia comunicazioni interne**.
    
      - Per controllare l'archiviazione delle comunicazioni esterne per i criteri utente, selezionare o deselezionare la casella di controllo **Archivia comunicazioni esterne**.

6.  Fare clic su **Commit**.

I criteri utente si applicano solo agli utenti a cui vengono assegnati. Per informazioni dettagliate sull'applicazione di un criterio utente a utenti specifici, vedere [applicazione di un criterio di archiviazione di Lync Server a un utente in Lync server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) nella documentazione relativa alla distribuzione.

</div>

</div>

<span> </span>

</div>

</div>

</div>

