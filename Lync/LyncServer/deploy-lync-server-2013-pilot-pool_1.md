---
title: Distribuire il pool pilota di Lync Server 2013
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
ms.openlocfilehash: 3df30b2aa45fe9519d724f904e8b375bed794042
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502958"
---
# <a name="deploy-lync-server-2013-pilot-pool"></a>Distribuire il pool pilota di Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-11-22_

Uno dei primi passaggi necessari per la migrazione a Lync Server 2013 è la distribuzione di un pool pilota. Il pool pilota è il luogo in cui è possibile testare la coesistenza di Lync Server 2013 con la distribuzione di Office Communications Server 2007 R2. La coesistenza è uno stato temporaneo che dura fino a quando non sono stati spostati tutti gli utenti e i pool in Lync Server 2013.

Quando si distribuisce un pool pilota, utilizzare la procedura guidata Definisci nuovo pool Front End. È consigliabile distribuire le stesse caratteristiche e i carichi di lavoro nel pool pilota di Lync Server 2013 che è presente nel pool di Office Communications Server 2007 R2. Se è stato distribuito il server di archiviazione, il Monitoring Server o System Center Operations Manager per l'archiviazione o il monitoraggio dell'ambiente Office Communications Server 2007 R2 e si desidera continuare l'archiviazione o il monitoraggio durante la migrazione, è necessario distribuire queste funzionalità anche nell'ambiente pilota. La versione distribuita per archiviare o monitorare l'ambiente Office Communications Server 2007 R2 non acquisisce i dati nell'ambiente Lync Server 2013.

<div>


> [!NOTE]  
> Nella procedura riportata di seguito vengono illustrate le funzionalità e le impostazioni che è necessario considerare come parte del processo complessivo di distribuzione del pool pilota. In questa sezione vengono evidenziati solo i punti chiave di cui è consigliabile tenere conto nell'ambito della distribuzione del pool pilota. Per la procedura dettagliata, vedere la guida alla distribuzione di <A href="lync-server-2013-deploying-lync-server.md">Lync Server 2013</A> .



</div>

**Per distribuire un pool pilota di Lync Server 2013**

1.  Accedere al computer in cui è installato Generatore di topologie come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.

2.  Aprire il Generatore di topologie e scegliere di creare una nuova topologia.

3.  Specificare il domino SIP primario.
    
    ![Creare una nuova topologia, definire la pagina del dominio principale](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "Creare una nuova topologia, definire la pagina del dominio principale")

4.  Continuare a eseguire la procedura guidata fino alla pagina **Definire il nuovo pool Front End**. Fare clic su Avanti.

5.  Immettere l'FQDN del pool. Quando si definisce il pool pilota, è possibile scegliere di distribuire un pool Enterprise Edition front end o un server Standard Edition. Lync Server 2013 non richiede che le funzionalità del pool pilota corrispondano a quelle distribuite nel pool legacy.
    
    <div>
    

    > [!WARNING]  
    > Il nome di dominio completo (FQDN) del pool o del server definito per il pool pilota deve essere univoco. Non può corrispondere al nome del pool di Office Communications Server 2007 R2 correntemente distribuito o di qualsiasi altro server attualmente distribuito.

    
    </div>
    
    ![Definire la pagina FQDN del pool Front End](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "Definire la pagina FQDN del pool Front End")

6.  Definire il computer che verrà aggiunto al pool.
    
    ![Definire una nuova finestra di dialogo del pool Front End](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "Definire una nuova finestra di dialogo del pool Front End")

7.  Nella pagina **Selezionare funzionalità** selezionare le caselle di controllo relative alle funzionalità che si desidera distribuire in questo pool Front End. Se ad esempio si distribuiscono solo le funzionalità di Messaggistica istantanea e presenza, si selezionerà la casella di controllo per il servizio di conferenza in modo da consentire sessioni IM tra più utenti, ma non quelle relative a funzionalità per conferenze vocali, video e collaborative come Conferenza con accesso esterno (PSTN), VoIP aziendale o Controllo di ammissione di chiamata. Per ulteriori informazioni sulla selezione di funzionalità, vedere [define and Configure a front end pool or Standard Edition server in Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) nella documentazione relativa alla distribuzione.
    
    ![Pagina di selezione delle funzionalità del pool Front End](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Pagina di selezione delle funzionalità del pool Front End")

8.  Nella pagina **Selezione ruoli server collocati** , è consigliabile collocare il Mediation Server in Lync Server 2013. Durante l'Unione di una topologia legacy con Lync Server 2013, è necessario innanzitutto collocare Office Communications Server 2007 R2 Mediation Server. Dopo l'Unione delle topologie e la configurazione di Lync Server 2013 Mediation Server, è possibile decidere se mantenere il Mediation Server collocato o modificarlo in un server autonomo quando si sposta il ruolo Mediation Server in Lync Server 2013 più avanti nel processo di distribuzione.
    
    ![Pagina di selezione dei ruoli server collocati nel pool Front End](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Pagina di selezione dei ruoli server collocati nel pool Front End")

9.  Nella pagina **Associare ruoli server al pool Front End** non scegliere l'opzione **Abilita un pool di server perimetrali utilizzato dal componente multimediale di questo pool Front End** durante la distribuzione del pool pilota. Questa funzionalità verrà abilitata e portata online in una fase successiva della migrazione, pertanto mantenere deselezionata questa opzione per ora.
    
    ![Associare i ruoli del server alla pagina del pool Front End](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Associare i ruoli del server alla pagina del pool Front End")

10. Nella pagina **Selezionare un server Office Web Apps** fare clic su **Nuovo** e specificare l'FQDN del server applicazioni.
    
    ![Definire nuove proprietà FQDN del server Office Web Apps](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Definire nuove proprietà FQDN del server Office Web Apps")

11. Nella pagina **definire l'archivio SQL Server di archiviazione** selezionare l'istanza di SQL Server creata in precedenza per Lync Server 2013.
    
    ![Pagina per la definizione dell'archivio SQL Server di archiviazione](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Pagina per la definizione dell'archivio SQL Server di archiviazione")

12. Nella pagina **definire l'archivio SQL Server di monitoraggio** selezionare l'istanza di SQL Server creata in precedenza per Lync Server 2013. Fare clic su **Fine**.

13. Nel nodo principale del Generatore di topologie fare clic con il pulsante destro del mouse su **Lync Server** e scegliere **Modifica proprietà.** Fare clic su **URL semplici**.

14. Aggiornare l'**URL di accesso amministrativo**.
    
    ![Modifica proprietà, pagina URL semplici](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "Modifica proprietà, pagina URL semplici")
    
    Per ulteriori informazioni sugli URL semplici, vedere l'argomento [Edit or Configure Simple URLs in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) nella documentazione relativa alla distribuzione.

15. In **Modifica proprietà** fare clic su **Server di gestione centrale**.

16. Nell'elenco a discesa selezionare il pool Lync Server 2013.
    
    ![Modifica proprietà, pagina server di gestione centrale](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "Modifica proprietà, pagina server di gestione centrale")

17. Fare clic su OK per chiudere la pagina **Modifica proprietà**.

18. Nel menu **Azione** scegliere **Pubblica topologia**.

19. Al termine del processo di pubblicazione, fare clic su **Fine**.

20. Tornando alla distribuzione guidata di Lync Server 2013, fare clic su **Installa o aggiorna il sistema Lync Server**.
    
    ![Distribuzione guidata di Lync Server 2013](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Distribuzione guidata di Lync Server 2013")

Per installare una copia locale dell'archivio di configurazione e avviare i servizi richiesti, vedere [Setting up front end servers and front end pools for Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) nella documentazione relativa alla distribuzione.


</div>

<span> </span>

</div>

</div>

</div>

