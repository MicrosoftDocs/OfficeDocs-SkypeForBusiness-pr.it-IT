---
title: Eseguire la migrazione dei numeri di accesso esterno
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: e0dfaed2-64c7-45cb-aaa9-d6117a26625d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721909(v=OCS.15)
ms:contentKeyID: 49733843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e808e587c9bd65668e35eba46692591bf72b9c0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210020"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a>Eseguire la migrazione dei numeri di accesso esterno

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-19_

La migrazione dei numeri di accesso esterno da Lync Server 2010 a Lync Server 2013 richiede l'esecuzione del cmdlet **Move-CsApplicationEndpoint** per eseguire la migrazione degli oggetti contatto. Durante il periodo di coesistenza di Lync Server 2010 e Lync Server 2013, i numeri di accesso esterno creati in Lync Server 2013 si comportano in modo analogo ai numeri di accesso esterno che si creano in Lync Server 2010, come descritto in questa sezione.

I numeri di accesso esterno creati in Lync Server 2010 ma spostati in Lync Server 2013 o creati in Lync Server 2013 prima, durante o dopo la migrazione hanno le caratteristiche seguenti:

  - Non sono visualizzati negli inviti alle riunioni di Office Communications Server 2007 R2 e nella pagina del numero di accesso esterno.

  - Sono visualizzati negli inviti alle riunioni di Lync Server 2010 e nella pagina del numero di accesso esterno.

  - Sono visualizzati negli inviti alle riunioni di Lync Server 2013 e nella pagina del numero di accesso esterno.

  - Possono essere visualizzati e modificati nello strumento di amministrazione di Office Communications Server 2007 R2.

  - Possono essere visualizzati e modificati nel Pannello di controllo di Lync Server 2010 e in Lync Server 2010 Management Shell.

  - Possono essere visualizzati e modificati nel Pannello di controllo di Lync Server 2013 e in Lync Server 2013 Management Shell.

  - Possono essere risequenziati nell'area tramite il cmdlet Set-CsDialinConferencingAccessNumber con il parametro Priority.

È necessario completare la migrazione dei numeri di accesso esterno che puntano a un pool di Lync Server 2010 prima di rimuovere il pool di Lync Server 2010. Se non si completa la migrazione come descritto nella procedura seguente, le chiamate in arrivo ai numeri di accesso avranno esito negativo.

<div>


> [!IMPORTANT]  
> È necessario eseguire questa procedura prima di rimuovere il pool Lync Server 2010.



</div>

<div>


> [!NOTE]  
> È consigliabile spostare i numeri di accesso esterno quando l'utilizzo della rete è ridotto, nel caso si verifichi una breve interruzione dei servizi.



</div>

**Per identificare e spostare i numeri di accesso esterno**

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Per spostare ogni numero di accesso esterno in un pool ospitato in Lync Server 2013, dalla riga di comando eseguire:
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

3.  Aprire il Pannello di controllo di Lync Server.

4.  Sulla barra di spostamento sinistra fare clic su **Servizio di conferenza**.

5.  Fare clic sulla scheda **Numero di accesso esterno**.

6.  Verificare che non rimangano numeri di accesso esterno per il pool di Lync Server 2010 da cui si esegue la migrazione.
    
    <div>
    

    > [!NOTE]  
    > Quando tutti i numeri di accesso esterno puntano al pool di Lync Server 2013, è possibile rimuovere il pool Lync Server 2010.

    
    </div>

**Verificare la migrazione dei numeri di accesso esterno tramite il Pannello di controllo di Lync Server**

1.  Da un account utente assegnato al ruolo **CsUserAdministrator** o al ruolo **CsAdministrator** accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire il Pannello di controllo di Lync Server.

3.  Sulla barra di spostamento sinistra fare clic su **Servizio di conferenza**.

4.  Fare clic sulla scheda **Numero di accesso esterno**.

5.  Verificare che tutti i numeri di accesso esterno vengano migrati nel pool ospitato in Lync Server 2013.

**Verificare la migrazione dei numeri di accesso esterno tramite Lync Server Management Shell**

1.  Aprire Lync Server Management Shell.

2.  Per ottenere un elenco di tutti i numeri di accesso a conferenze telefoniche con accesso esterno di cui è stata eseguita la migrazione, dalla riga di comando eseguire:
    
        Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}

3.  Verificare che tutti i numeri di accesso esterno vengano migrati nel pool ospitato in Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

