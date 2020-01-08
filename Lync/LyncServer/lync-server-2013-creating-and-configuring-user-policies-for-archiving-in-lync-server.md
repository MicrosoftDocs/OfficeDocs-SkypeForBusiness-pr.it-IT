---
title: Creazione e configurazione di criteri utente per l'archiviazione in Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating and configuring user policies for Archiving in Lync Server
ms:assetid: 5af0e605-3563-4d6f-a3c6-511d204a3165
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204923(v=OCS.15)
ms:contentKeyID: 48184234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3adccda55d1ae033acf52d64b093e73fe81dad10
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978801"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-and-configuring-user-policies-for-archiving-in-lync-server-2013"></a>Creazione e configurazione di criteri utente per l'archiviazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-09_

Per abilitare o disabilitare l'archiviazione per utenti specifici ospitati in Lync Server, è necessario prima di tutto creare un criterio utente e quindi applicare il criterio a uno o più utenti o gruppi di utente. Per informazioni dettagliate sull'applicazione di criteri utente a utenti e gruppi utente specifici, vedere [applicazione di un criterio di archiviazione di Lync Server a un utente in Lync server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) nella documentazione relativa alla distribuzione.

Per informazioni dettagliate sul funzionamento dei criteri di archiviazione, ad esempio la gerarchia per i criteri globali, per il sito e per gli utenti, vedere funzionamento dell' [archiviazione in Lync Server 2013](lync-server-2013-how-archiving-works.md) nella documentazione relativa alla pianificazione, nella documentazione relativa alla distribuzione o nella documentazione delle operazioni.

<div>


> [!NOTE]
> Se è stata abilitata l'integrazione di Microsoft Exchange per la distribuzione, i criteri di blocco sul posto di Exchange controllano se l'archiviazione è abilitata per gli utenti ospitati in Exchange 2013 e le cassette postali vengono messe sul posto. Per informazioni dettagliate, vedere <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configurazione dei criteri per l'archiviazione in Lync server 2013 quando si usa l'integrazione di Exchange Server</A> nella documentazione relativa alla distribuzione.<BR>Devi specificare tutte le opzioni appropriate nelle configurazioni di archiviazione prima di abilitare l'archiviazione. Per informazioni dettagliate, vedere <A href="lync-server-2013-configuring-archiving-options.md">configurazione delle opzioni di archiviazione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.



</div>

<div>

## <a name="to-configure-an-archiving-policy-for-users-homed-on-lync-server"></a>Per configurare un criterio di archiviazione per gli utenti ospitati in Lync Server

1.  Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server 2013. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server 2013, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **criteri di archiviazione**.

4.  Fare clic su **Nuovo** e quindi su **Criteri utente**.

5.  In **nuovi criteri di archiviazione**eseguire le operazioni seguenti:
    
      - In **nome**specificare il nome per il criterio utente.
    
      - In **Descrizione**, fornisci informazioni sui criteri utente (ad esempio, criteri utente per il reparto legale).
    
      - Per controllare l'archiviazione delle comunicazioni interne per i criteri utente, selezionare o deselezionare la casella di controllo **Archivia comunicazioni interne** .
    
      - Per controllare l'archiviazione delle comunicazioni esterne per i criteri utente, selezionare o deselezionare la casella di controllo **Archivia comunicazioni esterne** .

6.  Fare clic su **Commit**.

Un criterio utente si applica solo agli utenti a cui si assegnano i criteri. Per informazioni dettagliate sull'applicazione di un criterio utente a utenti specifici, vedere [applicazione di un criterio di archiviazione di Lync Server a un utente in Lync server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) nella documentazione relativa alla distribuzione.

</div>

</div>

<span> </span>

</div>

</div>

</div>

