---
title: "Lync Server 2013: configurazione dei criteri globali per l'archiviazione"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the global policy for Archiving
ms:assetid: 58341d6b-c3ff-4dd9-b1c7-0048f33861ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204906(v=OCS.15)
ms:contentKeyID: 48184192
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c14cbb69ce620498e1d804483f97c47da37e8522
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734666"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-global-policy-for-archiving-in-lync-server-2013"></a>Configurazione dei criteri globali per l'archiviazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-09_

Quando si distribuiscono i server front-end, Lync Server crea un criterio globale per l'archiviazione. Per impostazione predefinita, l'archiviazione è disabilitata nel criterio globale. Il criterio globale controlla se l'archiviazione è abilitata per le comunicazioni interne ed esterne per l'intera distribuzione, a meno che non vengano configurati i criteri del sito o degli utenti, che eseguono l'override del criterio globale o se si usa l'integrazione di Microsoft Exchange per alcuni o tutti Gli utenti. Se si usa l'integrazione di Microsoft Exchange, il criterio globale non si applica agli utenti ospitati in Exchange 2013 e le cassette postali vengono inserite in blocco sul posto.

Per informazioni dettagliate sul funzionamento dei criteri di archiviazione, ad esempio la gerarchia per i criteri globali, per il sito e per gli utenti, vedere funzionamento [dell'archiviazione in Lync Server 2013](lync-server-2013-how-archiving-works.md) documentazione di pianificazione, documentazione di distribuzione o documentazione operativa.

<div>


> [!NOTE]  
> Se si Abilita l'integrazione di Microsoft Exchange per la distribuzione, i criteri di blocco sul posto di Exchange controllano se l'archiviazione è abilitata per gli utenti che si trovano in Exchange 2013 e le cassette postali sono inserite in blocco sul posto. Per informazioni dettagliate, vedere <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configurazione dei criteri per l'archiviazione in Lync server 2013 quando si usa l'integrazione di Exchange Server</A> nella documentazione relativa alla distribuzione.<BR>Devi specificare tutte le opzioni appropriate nelle configurazioni di archiviazione prima di abilitare l'archiviazione. Per informazioni dettagliate, vedere <A href="lync-server-2013-configuring-archiving-options.md">configurazione delle opzioni di archiviazione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.



</div>

<div>

## <a name="to-configure-the-global-policy-for-archiving-when-using-lync-server-archiving-databases"></a>Per configurare i criteri globali per l'archiviazione quando si usano i database di archiviazione di Lync Server

1.  Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server 2013. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server 2013, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **criteri di archiviazione**.

4.  Nella pagina **criteri di archiviazione** fare clic su **globale**, fare clic su **modifica**e quindi su **Mostra dettagli**.

5.  In **modifica criteri di archiviazione-globale**eseguire le operazioni seguenti:
    
      - In **nome**, se non si vuole usare il nome predefinito globale, specificare un nuovo nome per il criterio globale.
    
      - In **Descrizione**, fornisci informazioni sui criteri, ad esempio criteri globali per *divisioni*.
    
      - Per controllare l'archiviazione delle comunicazioni interne per tutti i siti e gli utenti non controllati in modo specifico tramite criteri del sito o criteri utente, selezionare o deselezionare la casella di controllo **Archivia comunicazioni interne** .
    
      - Per controllare l'archiviazione delle comunicazioni esterne per tutti i siti e gli utenti non controllati in modo specifico tramite criteri del sito o criteri utente, selezionare o deselezionare la casella di controllo **Archivia comunicazioni esterne** .

6.  Fare clic su **Commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

