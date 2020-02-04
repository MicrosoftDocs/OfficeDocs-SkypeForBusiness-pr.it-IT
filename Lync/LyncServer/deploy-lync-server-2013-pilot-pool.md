---
title: Distribuire Lync Server 2013 Pilot pool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: a81aba1e-e636-434b-8c56-4150435bb55d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205144(v=OCS.15)
ms:contentKeyID: 48185028
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbe36710ab0acee23af1d8b83adece108cf86c4d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722996"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-pilot-pool"></a>Distribuire Lync Server 2013 Pilot pool

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-11-22_

Uno dei primi passaggi necessari per la migrazione a Lync Server 2013 consiste nel distribuire un pool pilota. Il pool di piloti è il punto in cui è possibile testare la coesistenza di Lync Server 2013 con la distribuzione di Lync Server 2010. La coesistenza è uno stato temporaneo che dura fino a quando non si sono spostati tutti gli utenti e i pool in Lync Server 2013.

Quando si distribuisce un pool pilota, si usa la procedura guidata Definisci nuovo pool di front-end. È consigliabile distribuire le stesse funzionalità e i carichi di lavoro nel pool di piloti di Lync Server 2013 nel pool di Lync Server 2010. Se si è distribuito server di archiviazione, server di monitoraggio o System Center Operations Manager per l'archiviazione o il monitoraggio dell'ambiente Lync Server 2010 e si vuole continuare l'archiviazione o il monitoraggio durante la migrazione, è necessario distribuirli anche funzionalità nell'ambiente pilota. La versione distribuita per archiviare o monitorare l'ambiente Lync Server 2010 non acquisisce i dati nell'ambiente Lync Server 2013.

<div>


> [!NOTE]  
> La procedura seguente illustra le caratteristiche e le impostazioni da tenere in considerazione nell'ambito del processo di distribuzione del pool pilota globale. Questa sezione evidenzia solo i punti chiave da tenere in considerazione nell'ambito della distribuzione del pool pilota. Per la procedura dettagliata, vedere la guida alla distribuzione di <A href="lync-server-2013-deploying-lync-server.md">Lync Server 2013</A> .



</div>

**Per distribuire un pool di piloti di Lync Server 2013**

1.  Accedere al computer in cui è installato Generatore di topologia come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.

2.  Espandere l'albero fino a raggiungere i pool di front end di **Lync Server 2013** **Enterprise Edition**.

3.  Fare clic con il pulsante destro del mouse su pool **front-end Enterprise Edition**e scegliere **nuovo pool Front-End**.
    
    ![Sottomenu di selezione del pool di server del Generatore di topologie](images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "Sottomenu di selezione del pool di server del Generatore di topologie")

4.  Immettere il nome di dominio completo del pool. Quando si definisce il pool pilota, è possibile scegliere di distribuire un pool di front-end Enterprise Edition o un server Standard Edition. Lync Server 2013 non richiede che le caratteristiche del pool pilota corrispondano a quelle distribuite nel pool legacy.
    
    <div>
    

    > [!WARNING]  
    > Il nome di dominio completo (FQDN) del pool o del server definito per il pool pilota deve essere univoco. Non può corrispondere al nome del pool di Lync Server 2010 attualmente distribuito o di qualsiasi altro server attualmente distribuito.

    
    </div>
    
    ![Pagina per la definizione del nome di dominio completo della procedura guidata Definisci nuovo pool Front End](images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "Pagina per la definizione del nome di dominio completo della procedura guidata Definisci nuovo pool Front End")

5.  Nella pagina **selezionare le caratteristiche** selezionare le caselle di controllo relative alle caratteristiche desiderate in questo pool di front-end. Ad esempio, se si stanno distribuendo solo le funzionalità di messaggistica istantanea e presenza, è necessario selezionare la casella di controllo conferenza per consentire la messaggistica istantanea a più parti, ma non selezionare le caselle di controllo per le conferenze telefoniche con accesso esterno, VoIP aziendale o di ammissione alle chiamate. perché rappresentano funzionalità di conferenza vocale, video e collaborative. Per altre informazioni sulla selezione di funzionalità, vedere [definire e configurare un pool Front end o un server Standard Edition in Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) nella documentazione relativa alla distribuzione.
    
    ![Pagina per la selezione delle funzionalità del pool Front End](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Pagina per la selezione delle funzionalità del pool Front End")

6.  Nella pagina **Selezione ruoli server collocati** è consigliabile collocare il Mediation Server in Lync Server 2013. Quando si unisce una topologia legacy a Lync Server 2013, è necessario prima di tutto collocare il server di mediazione Lync Server 2010. Dopo l'Unione delle topologie e la configurazione di Lync Server 2013 Mediation Server, è possibile decidere se conservare il Mediation Server collocato o modificarlo in un server autonomo quando si sposta il ruolo di Mediation Server in Lync Server 2013 più avanti nella distribuzione processo.
    
    ![Pagina per la selezione dei ruoli server collocati del pool Front End](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Pagina per la selezione dei ruoli server collocati del pool Front End")

7.  Nella pagina **associa i ruoli del server con questa pagina del pool Front-End** , durante la distribuzione del pool pilota, non scegliere l'opzione **Abilita un pool di bordi da usare per il componente multimediale di questo pool di front-end** . Si tratta di una caratteristica che verrà abilitata e riportata online in una fase successiva della migrazione. Mantieni questa impostazione deselezionata per il momento.
    
    ![Pagina per l'associazione dei ruoli server al pool Front End](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Pagina per l'associazione dei ruoli server al pool Front End")

8.  Nella pagina **selezionare un server di Office Web Apps** fare clic su **nuovo**e specificare il nome di dominio completo del server applicazioni.
    
    ![Proprietà del nome di dominio completo di Definire un nuovo server Office Online](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Proprietà del nome di dominio completo di Definire un nuovo server Office Online")

9.  Nella pagina **Definisci archiviazione SQL Server Store** , quando si definisce l'archivio di SQL Server per l'archiviazione e il monitoraggio di Lync Server, selezionare l'istanza di SQL Server creata in precedenza per lync Server 2013.
    
    ![Pagina per la definizione dell'archivio SQL Server di archiviazione](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Pagina per la definizione dell'archivio SQL Server di archiviazione")

10. Per pubblicare la topologia, fare clic con il pulsante destro del mouse sul nodo **Lync Server** e quindi scegliere **Pubblica topologia**.
    
    ![Generatore di topologie con topologia configurata](images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "Generatore di topologie con topologia configurata")

11. Al termine del processo di pubblicazione, fare clic su **fine**.

Per installare una copia locale dell'archivio di configurazione e avviare i servizi necessari, vedere [configurazione dei server front-end e dei pool Front end per Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) nella documentazione relativa alla distribuzione.


</div>

<span> </span>

</div>

</div>

</div>

