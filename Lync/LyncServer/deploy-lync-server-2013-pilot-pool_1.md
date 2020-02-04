---
title: Distribuire Lync Server 2013 Pilot pool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: 19c27053-8b21-401f-ad91-75c2dd355e91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204718(v=OCS.15)
ms:contentKeyID: 48183539
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46e6d4bd34c20038e430323b0f78ccf4f918aa62
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724046"
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

Uno dei primi passaggi necessari per la migrazione a Lync Server 2013 consiste nel distribuire un pool pilota. Il pool di piloti è il punto in cui è possibile testare la coesistenza di Lync Server 2013 con la distribuzione di Office Communications Server 2007 R2. La coesistenza è uno stato temporaneo che dura fino a quando non si sono spostati tutti gli utenti e i pool in Lync Server 2013.

Quando si distribuisce un pool pilota, si usa la procedura guidata Definisci nuovo pool di front-end. È consigliabile distribuire le stesse funzionalità e i carichi di lavoro nel pool di piloti di Lync Server 2013 nel pool di Office Communications Server 2007 R2. Se si è distribuito server di archiviazione, server di monitoraggio o System Center Operations Manager per l'archiviazione o il monitoraggio dell'ambiente Office Communications Server 2007 R2 e si vuole continuare l'archiviazione o il monitoraggio durante la migrazione, è necessario distribuire anche queste funzionalità nell'ambiente pilota. La versione distribuita per archiviare o monitorare l'ambiente Office Communications Server 2007 R2 non acquisisce i dati nell'ambiente Lync Server 2013.

<div>


> [!NOTE]  
> La procedura seguente illustra le caratteristiche e le impostazioni da tenere in considerazione nell'ambito del processo di distribuzione del pool pilota globale. Questa sezione evidenzia solo i punti chiave da tenere in considerazione nell'ambito della distribuzione del pool pilota. Per la procedura dettagliata, vedere la guida alla distribuzione di <A href="lync-server-2013-deploying-lync-server.md">Lync Server 2013</A> .



</div>

**Per distribuire un pool di piloti di Lync Server 2013**

1.  Accedere al computer in cui è installato Generatore di topologia come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.

2.  Aprire Generatore di topologie e scegliere di creare una nuova topologia.

3.  Immettere il dominio SIP principale.
    
    ![Crea nuova topologia - Pagina per la definizione del dominio primario](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "Crea nuova topologia - Pagina per la definizione del dominio primario")

4.  Continuare a completare la procedura guidata fino a raggiungere la procedura guidata **Definisci il nuovo pool Front-End** . Fare clic su Avanti.

5.  Immettere il nome di dominio completo del pool. Quando si definisce il pool pilota, è possibile scegliere di distribuire un pool di front-end Enterprise Edition o un server Standard Edition. Lync Server 2013 non richiede che le caratteristiche del pool pilota corrispondano a quelle distribuite nel pool legacy.
    
    <div>
    

    > [!WARNING]  
    > Il nome di dominio completo (FQDN) del pool o del server definito per il pool pilota deve essere univoco. Non può corrispondere al nome del pool di Office Communications Server 2007 R2 attualmente distribuito o di qualsiasi altro server attualmente distribuito.

    
    </div>
    
    ![Pagina Definire l'FQDN del pool Front End](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "Pagina Definire l'FQDN del pool Front End")

6.  Definire il computer che verrà aggiunto al pool.
    
    ![Finestra di dialogo Definisci nuovo pool Front End](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "Finestra di dialogo Definisci nuovo pool Front End")

7.  Nella pagina **selezionare le caratteristiche** selezionare le caselle di controllo relative alle caratteristiche desiderate in questo pool di front-end. Ad esempio, se si stanno distribuendo solo le funzionalità di messaggistica istantanea e presenza, è necessario selezionare la casella di controllo conferenza per consentire la messaggistica istantanea a più parti, ma non selezionare le caselle di controllo per le conferenze telefoniche con accesso esterno, VoIP aziendale o di ammissione alle chiamate. perché rappresentano funzionalità di conferenza vocale, video e collaborative. Per altre informazioni sulla selezione di funzionalità, vedere [definire e configurare un pool Front end o un server Standard Edition in Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) nella documentazione relativa alla distribuzione.
    
    ![Pagina per la selezione delle funzionalità del pool Front End](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Pagina per la selezione delle funzionalità del pool Front End")

8.  Nella pagina **Selezione ruoli server collocati** è consigliabile collocare il Mediation Server in Lync Server 2013. Quando si unisce una topologia legacy a Lync Server 2013, è necessario prima di tutto collocare Office Communications Server 2007 R2 Mediation Server. Dopo l'Unione delle topologie e la configurazione di Lync Server 2013 Mediation Server, è possibile decidere se conservare il Mediation Server collocato o modificarlo in un server autonomo quando si sposta il ruolo di Mediation Server in Lync Server 2013 più avanti nella distribuzione processo.
    
    ![Pagina per la selezione dei ruoli server collocati del pool Front End](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Pagina per la selezione dei ruoli server collocati del pool Front End")

9.  Nella pagina **associa i ruoli del server con questa pagina del pool Front-End** , durante la distribuzione del pool pilota, non scegliere l'opzione **Abilita un pool di bordi da usare per il componente multimediale di questo pool di front-end** . Si tratta di una caratteristica che verrà abilitata e riportata online in una fase successiva della migrazione. Mantieni questa impostazione deselezionata per il momento.
    
    ![Pagina per l'associazione dei ruoli server al pool Front End](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Pagina per l'associazione dei ruoli server al pool Front End")

10. Nella pagina **selezionare un server di Office Web Apps** fare clic su **nuovo**e specificare il nome di dominio completo del server applicazioni.
    
    ![Proprietà del nome di dominio completo di Definire un nuovo server Office Online](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Proprietà del nome di dominio completo di Definire un nuovo server Office Online")

11. Nella pagina **Definisci archiviazione SQL Server Store** selezionare l'istanza di SQL Server creata in precedenza per Lync Server 2013.
    
    ![Pagina per la definizione dell'archivio SQL Server di archiviazione](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Pagina per la definizione dell'archivio SQL Server di archiviazione")

12. Nella pagina **Definisci il monitoraggio di SQL Server Store** selezionare l'istanza di SQL Server creata in precedenza per Lync Server 2013. Fare clic su **fine**.

13. Dal nodo superiore di generatore di topologie fare clic con il pulsante destro del mouse su **Lync Server** e scegliere **modifica proprietà.** Fare clic su **URL semplici**.

14. Aggiornare l' **URL di accesso amministrativo**.
    
    ![Modifica proprietà - Pagina URL semplici](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "Modifica proprietà - Pagina URL semplici")
    
    Per altre informazioni sugli URL semplici, vedere l'argomento [modificare o configurare gli URL semplici in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) nella documentazione relativa alla distribuzione.

15. Dalle **proprietà modifica**fare clic su **server di gestione centrale**.

16. Nell'elenco a discesa selezionare il pool di Lync Server 2013.
    
    ![Modifica proprietà - Pagina Server di gestione centrale](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "Modifica proprietà - Pagina Server di gestione centrale")

17. Fare clic su OK per chiudere **la pagina Modifica proprietà** .

18. Scegliere **Pubblica topologia**dal menu **azione** .

19. Al termine del processo di pubblicazione, fare clic su **fine**.

20. Tornando alla distribuzione guidata di Lync Server 2013, fare clic su **Installa o aggiorna Lync Server System**.
    
    ![Distribuzione guidata di Lync Server 2013](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Distribuzione guidata di Lync Server 2013")

Per installare una copia locale dell'archivio di configurazione e avviare i servizi necessari, vedere [configurazione dei server front-end e dei pool Front end per Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) nella documentazione relativa alla distribuzione.


</div>

<span> </span>

</div>

</div>

</div>

