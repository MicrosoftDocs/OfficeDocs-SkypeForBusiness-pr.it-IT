---
title: "Lync Server 2013: configurazione dei criteri del sito per l'archiviazione"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up site policies for Archiving
ms:assetid: dc2ea206-8b9c-44dd-a479-efb217593c89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205325(v=OCS.15)
ms:contentKeyID: 48185613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08a4ccd7f88f21aaf0c7e3d1575b9e4a887c31d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-site-policies-for-archiving-in-lync-server-2013"></a>Configurazione dei criteri del sito per l'archiviazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-09_

È possibile abilitare o disabilitare l'archiviazione per siti specifici creando e configurando un criterio di archiviazione per ognuno di questi siti. Un criterio di sito sostituisce il criterio globale, ma i criteri utente sostituiscono i criteri del sito. I criteri di archiviazione si applicano solo se non si usa l'integrazione di Microsoft Exchange o, se si usa l'integrazione di Microsoft Exchange, ma alcuni utenti non sono residenti in Exchange 2013 e le cassette postali vengono inserite nel blocco sul posto.

Per informazioni dettagliate sul funzionamento dei criteri di archiviazione, ad esempio la gerarchia per i criteri globali, per il sito e per gli utenti, vedere funzionamento [dell'archiviazione in Lync Server 2013](lync-server-2013-how-archiving-works.md) documentazione di pianificazione, documentazione di distribuzione o documentazione operativa.

<div>


> [!NOTE]  
> Se si Abilita l'integrazione di Microsoft Exchange per la distribuzione, i criteri di blocco sul posto di Exchange controllano se l'archiviazione è abilitata per gli utenti che si trovano in Exchange 2013 e le cassette postali sono inserite in blocco sul posto. Per informazioni dettagliate, vedere <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configurazione dei criteri per l'archiviazione in Lync server 2013 quando si usa l'integrazione di Exchange Server</A> nella documentazione relativa alla distribuzione.<BR>Devi specificare tutte le opzioni appropriate nelle configurazioni di archiviazione prima di abilitare l'archiviazione di comunicazioni interne o esterne nei criteri di archiviazione. Per informazioni dettagliate, vedere <A href="lync-server-2013-configuring-archiving-options.md">configurazione delle opzioni di archiviazione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.



</div>

<div>

## <a name="to-create-an-archiving-policy-for-a-site"></a>Per creare criteri di archiviazione per un sito

1.  Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server 2013.

3.  Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **criteri di archiviazione**.
    
    Per informazioni dettagliate sul funzionamento dei criteri di archiviazione, ad esempio la gerarchia per i criteri globali, per il sito e per gli utenti, vedere funzionamento [dell'archiviazione in Lync Server 2013](lync-server-2013-how-archiving-works.md) documentazione di pianificazione, documentazione di distribuzione o documentazione operativa.

4.  Fare clic su **Nuovo** e quindi su **Criteri sito**.

5.  In **Seleziona un sito**fare clic sul sito a cui applicare il criterio.

6.  In **nuovi criteri di archiviazione**eseguire le operazioni seguenti:
    
      - In **nome**specificare il nome per il criterio del sito.
    
      - In **Descrizione**immettere informazioni sui criteri del sito, ad esempio i criteri del sito per Redmond.
    
      - Per controllare l'archiviazione delle comunicazioni interne per il sito specificato, selezionare o deselezionare la casella di controllo **Archivia comunicazioni interne** .
    
      - Per controllare l'archiviazione delle comunicazioni esterne per il sito specificato, selezionare o deselezionare la casella di controllo **Archivia comunicazioni esterne** .

7.  Fare clic su **Commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

