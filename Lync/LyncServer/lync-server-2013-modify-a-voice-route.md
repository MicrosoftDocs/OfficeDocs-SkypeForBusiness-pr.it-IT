---
title: 'Lync Server 2013: modificare una route vocale'
description: 'Lync Server 2013: modificare una route vocale.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a voice route
ms:assetid: afc562cc-8807-489b-8850-dbbe1c1ab9f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412838(v=OCS.15)
ms:contentKeyID: 48185143
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0aa507f3d0f459dd200b9c772f3a330d7da36197
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546412"
---
# <a name="modify-a-voice-route-in-lync-server-2013"></a>Modificare una route vocale in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

In questo argomento viene illustrato come modificare una route vocale. Per creare una nuova route, vedere [Create a Voice Route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).

<div>

## <a name="to-modify-a-voice-route"></a>Per modificare una route vocale

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Routing vocale** e quindi su **Route**.

4.  Nella pagina **Route** utilizzare uno dei metodi seguenti per modificare una route vocale:
    
      - Fare clic sul nome di una route vocale, fare clic su **Modifica**, quindi su **Mostra dettagli**.
    
      - Fare clic sul nome di una route vocale, fare clic su **Modifica**, su **Copia**, quindi su **Incolla**. Fare clic sulla nuova copia della route vocale appena creata, fare clic su **Modifica**, quindi su **Mostra dettagli**.

5.  Nel campo **Nome** della pagina **Modifica route vocale** digitare un nome descrittivo per la route vocale.

6.  Nel campo **Descrizione** digitare altre informazioni descrittive per la route vocale (facoltativo).

7.  Per specificare i formati che questa route deve includere, è possibile utilizzare lo strumento **Formato per corrispondenza** per generare un'espressione regolare oppure scrivere tale espressione manualmente.
    
      - Per utilizzare lo strumento **Formato per corrispondenza** per generare un'espressione regolare, immettere i valori come indicato di seguito. È possibile specificare due tipi di corrispondenze di formato:
        
          - **Cifre iniziali per i numeri che si desidera consentire:** Immettere i valori di prefisso che questa route deve contenere (incluso il + iniziale se necessario). Digitare, ad esempio, **+425** e quindi fare clic su **Aggiungi**. Ripetere questa operazione per ogni valore di prefisso da includere nella route.
        
          - **Eccezioni:** Se si desidera specificare una o più eccezioni per un valore di prefisso, evidenziare il prefisso e fare clic su **eccezioni**. Digitare uno o più valori per i formati di corrispondenza che la route *non* deve includere. Ad esempio, per escludere i numeri che iniziano con + 425237 dalla Route, immettere il valore **+ 425237** nel campo **eccezioni** e quindi fare clic su **OK**.
    
      - Per definire manualmente il formato di corrispondenza, fare clic su **Modifica** nello strumento **Formato per corrispondenza** e quindi digitare un'espressione regolare .NET Framework per specificare il formato di corrispondenza per i numeri di telefono di destinazione ai quali viene applicata la route. Per informazioni su come scrivere espressioni regolari, vedere la sezione relativa alle espressioni regolari di .NET Framework all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927) .

8.  Selezionare Ignora **ID chiamante** se non si desidera che l'ID del telefono che rende la chiamata in uscita venga visualizzato al destinatario della chiamata. Se si seleziona questa opzione, è necessario specificare un **ID chiamante alternativo** che verrà visualizzato sullo schermo dell'ID chiamante del destinatario.

9.  Per associare uno o più trunk PSTN (Public Switched Telephone Network) alla route vocale, fare clic su **Aggiungi**e quindi selezionare un trunk dall'elenco.
    
    <div>
    

    > [!NOTE]  
    > Se la distribuzione include tutti i Mediation Server di Microsoft Office Communications Server 2007 R2, saranno disponibili anche nell'elenco.

    
    </div>

10. Per associare uno o più utilizzi PSTN alla route vocale, fare clic su **Seleziona** e scegliere un record nell'elenco dei record di utilizzo PSTN definiti per la distribuzione di VoIP aziendale.
    
    <div>
    

    > [!NOTE]  
    > Per visualizzare le proprietà di ognuno dei record di utilizzo PSTN disponibili, vedere <A href="lync-server-2013-view-pstn-usage-records.md">visualizzare i record di utilizzo PSTN in Lync Server 2013</A>.<BR>Per creare o modificare i record di utilizzo PSTN, vedere <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">creare un criterio vocale e configurare i record di utilizzo PSTN in Lync server 2013</A> o <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">modificare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013</A>.

    
    </div>

11. Disporre i record di utilizzo PSTN per garantire prestazioni ottimali. Per modificare la posizione di un record nell'elenco, evidenziare il nome del record e fare clic sulla freccia in su o in giù.
    
    <div>
    

    > [!NOTE]  
    > A differenza di un criterio vocale in cui l'ordine in cui sono elencati i record di utilizzo PSTN è importante, l'ordine dei record di utilizzo PSTN in una route vocale è insignificante. È tuttavia consigliabile organizzare l'elenco per frequenza di utilizzo, ad esempio: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Lync Server attraversa l'elenco dall'alto verso il basso).

    
    </div>

12. Digitare un valore nel campo **Numero convertito da testare** e fare clic su **Vai**. I risultati del test vengono visualizzati nel campo (facoltativo).
    
    <div>
    

    > [!NOTE]  
    > È possibile salvare una route vocale che non passa ancora il test e quindi riconfigurarla successivamente. Per ulteriori informazioni, vedere <A href="lync-server-2013-test-voice-routing.md">test Voice routing in Lync Server 2013</A>.

    
    </div>

13. Fare clic su **OK**.

14. Nella pagina **Route** fare clic su **Commit** e quindi su **Salva tutto**.
    
    <div>
    

    > [!NOTE]  
    > Ogni volta che si crea o si modifica una route vocale, è necessario eseguire il comando <STRONG>Commit all</STRONG> per pubblicare la modifica della configurazione. Per ulteriori informazioni, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013</A> nella documentazione relativa alle operazioni.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creare una route vocale in Lync Server 2013](lync-server-2013-create-a-voice-route.md)  
[Visualizzare i record di utilizzo PSTN in Lync Server 2013](lync-server-2013-view-pstn-usage-records.md)  
[Creare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[Modificare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[Pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Testare il routing vocale in Lync Server 2013](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

