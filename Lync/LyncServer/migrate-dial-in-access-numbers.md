---
title: Eseguire la migrazione dei numeri di accesso esterno
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate dial-in access numbers
ms:assetid: e0dfaed2-64c7-45cb-aaa9-d6117a26625d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721909(v=OCS.15)
ms:contentKeyID: 49733843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4f0f286450aeaaf747d4642bf8791695d16b603
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981489"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a>Eseguire la migrazione dei numeri di accesso esterno

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-19_

La migrazione dei numeri di accesso esterno da Lync Server 2010 a Lync Server 2013 richiede l'esecuzione del cmdlet **Move-CsApplicationEndpoint** per eseguire la migrazione degli oggetti contatto. Durante il periodo di coesistenza di Lync Server 2010 e Lync Server 2013, i numeri di accesso esterno creati in Lync Server 2013 si comportano in modo analogo ai numeri di accesso per la chiamata in ingresso che si creano in Lync Server 2010, come descritto in questa sezione.

I numeri di accesso esterno creati in Lync Server 2010 ma spostati in Lync Server 2013 o creati in Lync Server 2013 prima che durante o dopo la migrazione abbiano le caratteristiche seguenti:

  - Non vengono visualizzati negli inviti alle riunioni di Office Communications Server 2007 R2 e nella pagina numero di accesso esterno.

  - Vengono visualizzati negli inviti alle riunioni di Lync Server 2010 e nella pagina numero di accesso esterno.

  - Vengono visualizzati negli inviti alle riunioni di Lync Server 2013 e nella pagina numero di accesso esterno.

  - Non è possibile visualizzare o modificare lo strumento di amministrazione di Office Communications Server 2007 R2.

  - Può essere visualizzato e modificato nel pannello di controllo di Lync Server 2010 e in Lync Server 2010 Management Shell.

  - Può essere visualizzato e modificato nel pannello di controllo di Lync Server 2013 e in Lync Server 2013 Management Shell.

  - Può essere risequenziata all'interno dell'area geografica usando il cmdlet Set-CsDialinConferencingAccessNumber con il parametro Priority.

È necessario completare la migrazione dei numeri di accesso esterno che puntano a un pool di Lync Server 2010 prima di rimuovere la Commissione dal pool di Lync Server 2010. Se non si completa la migrazione dei numeri di accesso per la chiamata in ingresso, come descritto nella procedura seguente, le chiamate in arrivo ai numeri di accesso avranno esito negativo.

<div>


> [!IMPORTANT]  
> È necessario eseguire questa procedura prima della disattivazione del pool di Lync Server 2010.



</div>

<div>


> [!NOTE]  
> È consigliabile trasferire i numeri di accesso esterno quando l'utilizzo della rete è basso, in caso di un breve periodo di interruzione del servizio.



</div>

**Per identificare e cambiare i numeri di accesso per la chiamata in ingresso**

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Per trasferire ogni numero di accesso esterno a un pool ospitato in Lync Server 2013, dalla riga di comando eseguire:
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

3.  Aprire il pannello di controllo di Lync Server.

4.  Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**.

5.  Fare clic sulla scheda **numero di accesso** esterno.

6.  Verificare che non siano presenti numeri di accesso per la chiamata in ingresso per il pool di Lync Server 2010 da cui si esegue la migrazione.
    
    <div>
    

    > [!NOTE]  
    > Quando tutti i numeri di accesso esterno puntano al pool di Lync Server 2013, è possibile rimuovere il pool di Lync Server 2010.

    
    </div>

**Verificare la migrazione dei numeri di accesso esterno tramite il pannello di controllo di Lync Server**

1.  Da un account utente assegnato al ruolo **CsUserAdministrator** o **CsAdministrator** , accedere a qualsiasi computer della distribuzione interna.

2.  Aprire il pannello di controllo di Lync Server.

3.  Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**.

4.  Fare clic sulla scheda **numero di accesso** esterno.

5.  Verificare che tutti i numeri di accesso per la chiamata in ingresso vengano migrati nel pool ospitati in Lync Server 2013.

**Verificare la migrazione dei numeri di accesso esterno tramite Lync Server Management Shell**

1.  Aprire Lync Server Management Shell.

2.  Per restituire tutti i numeri di accesso per le conferenze telefoniche con chiamata in ingresso migrati, dalla riga di comando eseguire:
    
        Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}

3.  Verificare che tutti i numeri di accesso per la chiamata in ingresso vengano migrati nel pool ospitati in Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

