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
ms.openlocfilehash: e6dcd2af235c161e3f35c675daf8494a2490fddd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040935"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-global-policy-for-archiving-in-lync-server-2013"></a>Configurazione dei criteri globali per l'archiviazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-09_

Quando si distribuisce i Front End Server, Lync Server crea un criterio globale per l'archiviazione. Per impostazione predefinita, nei criteri globali l'archiviazione è disabilitata. Il criterio globale determina se l'archiviazione è abilitata per le comunicazioni interne ed esterne per l'intera distribuzione, a meno che non si configurano i criteri di sito o utente, che sostituiscono il criterio globale, o se si utilizza l'integrazione di Microsoft Exchange per alcuni o tutti i Gli utenti. Se si utilizza l'integrazione di Microsoft Exchange, il criterio globale non si applica a tutti gli utenti ospitati in Exchange 2013 e le cassette postali vengono conservate sul posto.

Per informazioni dettagliate sul funzionamento dei criteri di archiviazione, inclusa la gerarchia per i criteri globali, sito e utente, vedere [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations Documentation.

<div>


> [!NOTE]  
> Se si Abilita l'integrazione di Microsoft Exchange per la distribuzione, i criteri di conservazione sul posto di Exchange controllano se l'archiviazione è abilitata per gli utenti che si trovano in Exchange 2013 e le relative cassette postali vengono conservate sul posto. Per informazioni dettagliate, vedere <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">impostazione dei criteri per l'archiviazione in Lync server 2013 quando si utilizza l'integrazione di Exchange Server</A> nella documentazione relativa alla distribuzione.<BR>Specificare tutte le opzioni appropriate nelle configurazioni di archiviazione prima di abilitare l'archiviazione. Per ulteriori informazioni, vedere <A href="lync-server-2013-configuring-archiving-options.md">configurazione delle opzioni di archiviazione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.



</div>

<div>

## <a name="to-configure-the-global-policy-for-archiving-when-using-lync-server-archiving-databases"></a>Per configurare i criteri globali per l'archiviazione usando database di archiviazione di Lync Server

1.  Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Lync Server 2013. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server 2013, vedere [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Criteri di archiviazione**.

4.  Nella pagina **Criteri di archiviazione**fare clic su **Globale**, **Modifica** e quindi su **Mostra dettagli**.

5.  In **Modifica Criteri di archiviazione - Globale** eseguire le operazioni seguenti:
    
      - In **Nome**, se non si vuole usare il nome predefinito Globale, specificare un nuovo nome per i criteri globali.
    
      - In **Descrizione** immettere le informazioni sui criteri, ad esempio "Criteri globali per *nomeDivisione*".
    
      - Per controllare l'archiviazione delle comunicazioni interne per tutti i siti e gli utenti non controllati in modo specifico tramite criteri utente o sito, selezionare o deselezionare la casella di controllo **Archivia comunicazioni interne**.
    
      - Per controllare l'archiviazione delle comunicazioni esterne per tutti i siti e gli utenti non controllati in modo specifico tramite criteri utente o di sito, selezionare o deselezionare la casella di controllo **Archivia comunicazioni esterne**.

6.  Fare clic su **Commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

