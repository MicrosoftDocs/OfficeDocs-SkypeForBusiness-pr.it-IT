---
title: Configurare le route di federazione e il traffico multimediale
description: Configurare le route di Federazione e il traffico multimediale.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: 8b2f5f81-a955-4ad1-ad74-397322ff9521
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688121(v=OCS.15)
ms:contentKeyID: 49733720
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de26f472bddc504ff79e427b5243587f27020c3d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542982"
---
# <a name="configure-federation-routes-and-media-traffic"></a>Configurare le route di federazione e il traffico multimediale

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-15_

La federazione è una relazione di trust tra due o più domini SIP che consente a utenti di organizzazioni distinte di comunicare attraverso i confini della rete. Dopo aver eseguito la migrazione al pool pilota di Lync Server 2013, è necessario eseguire la transizione dalla route di Federazione dei server perimetrali di Lync Server 2010 alla route di Federazione dei server perimetrali di Lync Server 2013.

Utilizzare le procedure seguenti per la transizione della route di Federazione e della route del traffico multimediale dal server perimetrale e dal Director di Lync Server 2010 al server perimetrale di Lync Server 2013, per una distribuzione a sito singolo.

<div>


> [!IMPORTANT]  
> La modifica della route di Federazione e della route del traffico multimediale richiede la pianificazione di tempi di inattività di manutenzione per i server perimetrali di Lync Server 2013 e Lync Server 2010. Il processo di transizione completo implica anche che l'accesso federato non sarà disponibile per l'intera durata dell'interruzione dei servizi. È consigliabile pianificare l'interruzione dei servizi in un lasso di tempo in cui si prevede un'attività minima da parte degli utenti. È inoltre consigliabile inviare notifica agli utenti con sufficiente anticipo. Pianificare adeguatamente l'interruzione dei servizi e fare in modo che le aspettative dell'organizzazione siano appropriate.



</div>

<div>


> [!IMPORTANT]  
> Se il server perimetrale Lync Server 2010 legacy è configurato per utilizzare lo stesso nome di dominio completo per il servizio Access Edge, il servizio Web Conferencing Edge e il servizio A/V Edge, le procedure descritte in questa sezione non sono supportate. Se i servizi perimetrali legacy sono configurati per l'utilizzo dello stesso FQDN, è necessario prima eseguire la migrazione di tutti gli utenti da Lync Server 2010 a Lync Server 2013, quindi rimuovere il server perimetrale di Lync Server 2010 prima di abilitare la Federazione sul server perimetrale di Lync Server 2013.



</div>

<div>


> [!IMPORTANT]  
> Se la Federazione XMPP viene instradata attraverso un server perimetrale di Lync Server 2013, gli utenti di Lync Server 2010 legacy non saranno in grado di comunicare con il partner federato XMPP finché tutti gli utenti non sono stati spostati in Lync Server 2013, sono stati configurati i criteri e i certificati XMPP, il partner federato XMPP è stato configurato su Lync Server 2013 e infine le voci DNS sono state aggiornate



</div>

<div>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a>Per rimuovere l'associazione di federazione legacy dai siti di Lync Server 2013

1.  Nel server front end di Lync Server 2013 aprire la topologia esistente in Generatore di topologie.

2.  Nel riquadro sinistro, passare la nodo del sito direttamente sotto **Lync Server**.

3.  Fare clic con il pulsante destro del mouse sul sito e quindi scegliere **Modifica proprietà **.

4.  Nel riquadro sinistro, selezionare **Route di federazione**.

5.  In **Assegnazione route federazione sito**deselezionare la casella di controllo **Abilita federazione SIP** per disabilitare la route di federazione tramite l'ambiente legacy di Lync Server 2010.
    
    ![Finestra di dialogo Modifica proprietà, pagina Route di Federazione](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "Finestra di dialogo Modifica proprietà, pagina Route di Federazione")

6.  Fare clic su  **OK** per chiudere la pagina Modifica proprietà.

7.  In **Generatore di topologie** selezionare il nodo di primo livello **Lync Server**.

8.  Scegliere **Pubblica topologia** dal menu **Azione**.

9.  Fare clic su **Avanti** per completare il processo di pubblicazione e quindi fare clic su **Fine** al termine del processo.

</div>

<div>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>Per configurare il server perimetrale legacy come server perimetrale non federato

1.  Nel riquadro sinistro, passare al nodo **Lync Server 2010** e quindi al nodo **Pool di server perimetrali**.

2.  Fare clic con il pulsante destro del mouse sul server perimetrale e quindi scegliere **Modifica proprietà**.

3.  Selezionare **Generale** nel riquadro sinistro.

4.  Deselezionare la casella di controllo **Abilita federazione per pool di server perimetrali (porta 5061)** e fare clic su **OK** per chiudere la pagina.
    
    ![Modifica proprietà, generale, deseleziona Abilita federazione](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "Modifica proprietà, generale, deseleziona Abilita federazione")

5.  Scegliere **Pubblica topologia** dal menu **Azione** e quindi scegliere **Avanti**.

6.  Al termine della **Pubblicazione guidata** fare clic su **Fine** per chiudere la procedura guidata.

7.  Verificare che la federazione del server perimetrale legacy sia disabilitata.
    
    ![Generatore di topologie, pool di server perimetrali, Federazione disabilitata](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "Generatore di topologie, pool di server perimetrali, Federazione disabilitata")

</div>

<div>

## <a name="to-configure-certificates-on-the-lync-server-2010-edge-server"></a>Per configurare i certificati nel server perimetrale di Lync Server 2010

1.  Esportare il certificato del proxy di accesso esterno con la chiave privata dal server perimetrale Lync Server 2010 legacy.

2.  Nel server perimetrale di Lync Server 2013 importare il certificato esterno del proxy di accesso dal passaggio precedente.

3.  Assegnare il certificato esterno del proxy di accesso all'interfaccia esterna di Lync Server 2013 del server perimetrale.

4.  Il certificato dell'interfaccia interna del server perimetrale di Lync Server 2013 deve essere richiesto da un'autorità di certificazione attendibile e assegnato.

</div>

<div>

## <a name="to-change-lync-server-2010-federation-route-to-use-lync-server-2013-edge-server"></a>Per modificare la route di federazione di Lync Server 2010 per l'uso del server perimetrale di Lync Server 2013

1.  Nel riquadro sinistro del Generatore di topologie, passare al nodo **Lync Server 2013 ** e quindi al nodo **Pool di server perimetrali**.

2.  Fare clic con il pulsante destro del mouse sul server perimetrale e quindi scegliere **Modifica proprietà**.

3.  Selezionare **Generale** nel riquadro sinistro.

4.  Selezionare la casella di controllo **Abilita federazione per pool di server perimetrali (porta 5061)** e quindi fare clic su **OK** per chiudere la pagina.
    
    ![Finestra di dialogo Modifica proprietà, pagina generale](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Finestra di dialogo Modifica proprietà, pagina generale")

5.  Scegliere **Pubblica topologia** dal menu **Azione** e quindi scegliere **Avanti**.

6.  Al termine della **Pubblicazione guidata** fare clic su **Fine** per chiudere la procedura guidata.

7.  Verificare che **Federazione (porta 5061)** sia impostata su **Abilitata**.
    
    ![Generatore di topologie, pool di server perimetrali, Federazione abilitata](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "Generatore di topologie, pool di server perimetrali, Federazione abilitata")

</div>

<div>

## <a name="to-update-lync-server-2013-edge-server-federation-next-hop"></a>Per aggiornare l'hop successivo di federazione del server perimetrale di Lync Server 2013

1.  Nel riquadro sinistro del Generatore di topologie, passare al nodo **Lync Server 2013 ** e quindi al nodo **Pool di server perimetrali**.

2.  Espandere il nodo, fare clic con il pulsante destro del mouse sul server perimetrale elencato e quindi scegliere  **Modifica proprietà **.

3.  In **selezione hop successivo**nella pagina **generale** selezionare nell'elenco a discesa il pool Lync Server 2013.
    
    ![Finestra di dialogo Modifica proprietà, pagina hop successivo](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "Finestra di dialogo Modifica proprietà, pagina hop successivo")

4.  Fare clic su  **OK** per chiudere la pagina Modifica proprietà.

5.  In **Generatore di topologie**selezionare il nodo di primo livello **Lync Server** .

6.  Scegliere **Pubblica topologia** dal menu **Azione** e completare la procedura guidata.

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a>Per configurare il percorso del contenuto multimediale in uscita dei server perimetrali Lync Server 2013

1.  In Generatore di topologie, nel riquadro sinistro, passare al nodo **Lync Server 2013** e quindi al pool al di sotto di **Standard Edition Front End Server** o **pool Enterprise Edition front end**.

2.  Fare clic con il pulsante destro del mouse sul pool e quindi scegliere  **Modifica proprietà **.

3.  Nella sezione  **Associazioni ** selezionare la casella di controllo  **Associa pool di server perimetrali (per componenti multimediali) **.
    
    ![Modifica proprietà, generale, associa pool di server perimetrali](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "Modifica proprietà, generale, associa pool di server perimetrali")

4.  Nella casella a discesa selezionare il server perimetrale di Lync Server 2013.

5.  Fare clic su  **OK ** per chiudere la pagina  **Modifica proprietà **.

</div>

<div>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a>Per abilitare la federazione del server perimetrale di Lync Server 2013

1.  Nel riquadro sinistro del Generatore di topologie, passare al nodo **Lync Server 2013 ** e quindi al nodo **Pool di server perimetrali**.

2.  Espandere il nodo, fare clic con il pulsante destro del mouse sul server perimetrale elencato e quindi scegliere  **Modifica proprietà **.
    
    <div>
    

    > [!NOTE]  
    > La Federazione può essere abilitata solo per un singolo pool di server perimetrali. In presenza di più pool di server perimetrali, selezionarne uno da utilizzare come pool di server perimetrali federati.

    
    </div>

3.  Nella pagina **Generale** verificare che l'impostazione **Abilita federazione per pool di server perimetrali (porta 5061)** sia selezionata.
    
    ![Finestra di dialogo Modifica proprietà, pagina generale](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Finestra di dialogo Modifica proprietà, pagina generale")

4.  Fare clic su  **OK** per chiudere la pagina Modifica proprietà.

5.  Passare quindi al nodo del sito.

6.  Fare clic con il pulsante destro del mouse sul sito e quindi scegliere  **Modifica proprietà **.

7.  Nel riquadro sinistro fare clic su  **Route di federazione **.

8.  In **Assegnazione route federazione sito**selezionare **Abilita federazione SIP**e quindi nell'elenco selezionare il server perimetrale di Lync Server 2013 elencato.
    
    ![Modifica proprietà, pagina Route di Federazione](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "Modifica proprietà, pagina Route di Federazione")

9.  Fare clic su  **OK ** per chiudere la pagina  **Modifica proprietà **.
    
    Nel caso di distribuzioni multisito, eseguire questa procedura in ogni sito.

</div>

<div>

## <a name="to-publish-edge-server-configuration-changes"></a>Per pubblicare le modifiche di configurazione del server perimetrale

1.  In **Generatore di topologie**selezionare il nodo di primo livello **Lync Server** .

2.  Scegliere **Pubblica topologia** dal menu **Azione** e completare la procedura guidata.

3.  Attendere il completamento della replica di Active Directory in tutti i pool della distribuzione.
    
    <div>
    

    > [!NOTE]  
    > Potrebbe essere visualizzato il messaggio seguente:<BR><STRONG>Avviso: la topologia contiene più di un server perimetrale federato. Questa situazione può verificarsi durante la migrazione a una versione successiva del prodotto. In questo caso, per la federazione viene utilizzato attivamente un solo server perimetrale. Verificare che il record SRV DNS punti al server perimetrale corretto. Se si desidera distribuire più server perimetrali federati in modo che siano attivi contemporaneamente (ovvero non in uno scenario di migrazione), verificare che tutti i partner federati utilizzino Lync Server e che il record SRV DNS esterno elenchi tutti i server perimetrali abilitati per la federazione</STRONG>.<BR>Si tratta di un avviso previsto che può essere tranquillamente ignorato.

    
    </div>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server"></a>Per configurare il server perimetrale Lync Server 2013

1.  Portare online tutti i server perimetrali di Lync Server 2013.

2.  Aggiornare le regole di routing del firewall esterno o le impostazioni del servizio di bilanciamento del carico hardware in modo da inviare il traffico SIP per l'accesso esterno (in genere la porta 443) e la Federazione (in genere la porta 5061) al server perimetrale di Lync Server 2013, anziché al server perimetrale legacy.
    
    <div>
    

    > [!NOTE]  
    > Se non si dispone di un servizio di bilanciamento del carico hardware, è necessario aggiornare il record A DNS per la federazione in modo che venga risolto nel nuovo server Access Edge Server di Lync Server. Per eseguire questa operazione causando una minima interruzione del servizio, ridurre il valore TLL per l'FQDN Access Edge di Lync Server esterno in modo che se il DNS viene aggiornato per puntare al nuovo Access Edge Server di Lync Server, la federazione e l'accesso remoto vengano aggiornati rapidamente.

    
    </div>

3.  Successivamente, arrestare **Lync Server Access Edge** da ogni computer server perimetrale.

4.  Da ogni computer server perimetrale legacy, aprire l'applet **Servizi** dagli **strumenti di amministrazione**.

5.  Nell'elenco di servizi, individuare **Lync Server Access Edge**.

6.  Fare clic con il pulsante destro del mouse sul nome del servizio e quindi scegliere **Arresta** per arrestarlo.

7.  Impostare il tipo di avvio su **Disabilitato**.

8.  Fare clic su  **OK ** per chiudere la finestra **Proprietà **.

</div>

</div>

<span> </span>

</div>

</div>

</div>

