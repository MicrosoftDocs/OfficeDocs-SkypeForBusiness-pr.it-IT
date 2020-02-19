---
title: 'Lync Server 2013: configurare i certificati per il Director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates for the Director
ms:assetid: 22988186-15ae-43b1-92f4-0adb3b75a7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398296(v=OCS.15)
ms:contentKeyID: 48183612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d64eac2708c2b7fc1f0bfd3ab26a9bd38581f54c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140469"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-the-director-in-lync-server-2013"></a>Configurare i certificati per il Director in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-08_

<div>


> [!IMPORTANT]  
> Quando si esegue la Configurazione guidata certificati, verificare di aver eseguito l'accesso con un account membro di un gruppo a cui sono state assegnate le autorizzazioni appropriate per il tipo di modello di certificato che verrà utilizzato. Per impostazione predefinita, una richiesta di certificato di Lync Server 2013 utilizzerà il modello di certificato del server Web. Se si utilizza un account membro del gruppo RTCUniversalServerAdmins per richiedere un certificato che utilizza questo modello, verificare che al gruppo siano state assegnate le autorizzazioni di registrazione necessarie per l'utilizzo del modello.



</div>

Ogni director richiede un certificato predefinito, un certificato Web interno e un certificato Web esterno. Per informazioni dettagliate sui requisiti dei certificati per i direttori, vedere [Certificate Requirements for Internal Servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) nella documentazione relativa alla pianificazione.

Utilizzare la procedura seguente per configurare i certificati per i Director. Ripetere la procedura per ogni Director. Nei passaggi di questa procedura viene descritto come configurare un certificato da un'autorità di certificazione (CA) radice globale (enterprise) interna distribuita dall'organizzazione e con l'elaborazione delle richieste offline. Per informazioni dettagliate su come ottenere certificati da una CA esterna, rivolgersi al team di supporto.

<div>

## <a name="to-configure-certificates-for-the-director-or-director-pool"></a>Per configurare certificati per il Director o il pool di server Director

1.  Nella distribuzione guidata di Lync Server, accanto a **passaggio 3: richiesta, installazione o assegnazione dei certificati**, fare clic su **Esegui**.

2.  Nella pagina **Configurazione guidata certificati** fare clic su **Richiesta**.

3.  Nella pagina **Richiesta di certificato** fare clic su **Avanti**.

4.  Nella pagina **Richiesta posticipata o immediata** accettare l'opzione predefinita **Invia immediatamente la richiesta a un'autorità di certificazione online** e quindi fare clic su **Avanti**.

5.  Nella pagina **Scegli Autorità di certificazione (CA)** fare clic sull'autorità di certificazione di Windows interna che si desidera utilizzare e quindi fare clic su **Avanti**.

6.  Nella pagina **Account autorità di certificazione** specificare credenziali alternative da utilizzare se l'account con cui è stato eseguito l'accesso non dispone dell'autorità sufficiente per richiedere il certificato e quindi fare clic su **Avanti**.

7.  Nella pagina **Specifica modello di certificato alternativo** fare clic su **Avanti**.

8.  Nella pagina **Impostazioni nome e sicurezza** è possibile specificare un nome in **Nome descrittivo**, accettare la lunghezza di chiave di 2048 bit e quindi fare clic su **Avanti**.

9.  Nella pagina **Informazioni sull'organizzazione** specificare facoltativamente le informazioni sull'organizzazione e quindi fare clic su **Avanti**.

10. Nella pagina **Dati geografici** specificare facoltativamente i dati geografici e quindi fare clic su **Avanti**.

11. Nella pagina **Nome soggetto / Nomi soggetto alternativi** fare clic su **Avanti**.
    
    <div>
    

    > [!NOTE]  
    > Nell'elenco dei nomi alternativi del soggetto dovrebbero essere contenuti il nome del computer in cui si desidera installare il Director (se singolo) o il nome del pool di server Director e i nomi degli URL semplici configurati per l'organizzazione.

    
    </div>

12. Nella pagina **Impostazione del dominio SIP su nomi soggetto alternativi (SAN)** selezionare **Domini SIP configurati** per tutti i domini che devono essere gestiti dal Director e quindi fare clic su **Avanti**.

13. Nella pagina **Configura nomi soggetto alternativi aggiuntivi** aggiungere altri eventuali nomi alternativi del soggetto necessari e quindi fare clic su **Avanti**.

14. Nella pagina **Riepilogo richiesta certificato** fare clic su **Avanti**.

15. Nella pagina **Esecuzione comandi in corso** fare clic su **Avanti** al termine dell'esecuzione dei comandi.

16. Nella pagina **Stato richiesta di certificato online** fare clic su **Fine**.

17. Nella pagina **Assegnazione certificato** fare clic su **Avanti**.
    
    <div>
    

    > [!NOTE]  
    > Se si desidera visualizzare il certificato, fare doppio clic su di esso nell'elenco.

    
    </div>

18. Nella pagina **Riepilogo assegnazione certificato** fare clic su **Avanti**.

19. Nella pagina **Esecuzione comandi in corso** fare clic su **Fine** al termine dell'esecuzione dei comandi.

20. Nella pagina **Configurazione guidata certificati** fare clic su **Chiudi**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

