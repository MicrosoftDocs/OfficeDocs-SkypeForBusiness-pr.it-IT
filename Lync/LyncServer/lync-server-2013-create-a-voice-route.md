---
title: 'Lync Server 2013: creare una route vocale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice route
ms:assetid: d189057d-cc9d-4622-9d10-f5385d703faf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398898(v=OCS.15)
ms:contentKeyID: 48185438
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f51c1df7807d30d2c8c97882db638febc78e78ab
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034768"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-voice-route-in-lync-server-2013"></a>Creare una route vocale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Nella procedura seguente viene illustrato come creare una nuova route vocale utilizzando il pannello di controllo di Lync Server 2013. Per modificare una route esistente, vedere [Modify a Voice Route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md) per la procedura.

<div>

## <a name="to-create-a-voice-route-by-using-the-lync-server-control-panel"></a>Per creare una route vocale tramite il pannello di controllo di Lync Server

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo amministrativo **CsVoiceAdministrator**, **CsServerAdministrator**o **CsAdministrator** .

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Routing vocale**.

4.  Fare clic su **Route**.

5.  Fare clic su **nuovo** per visualizzare la finestra di dialogo **nuova route vocale** .

6.  In **nome**Digitare un nome descrittivo per la route vocale.

7.  Optional In **Descrizione**digitare altre informazioni descrittive per la route vocale.

8.  Per specificare i modelli che si desidera vengano configurati per l'instradamento, è possibile utilizzare lo strumento **Crea un modello per la corrispondenza** per generare un'espressione regolare o scrivere manualmente l'espressione regolare.
    
      - Per utilizzare lo strumento **Formato per corrispondenza** per generare un'espressione regolare, immettere i valori come indicato di seguito. È possibile specificare due tipi di corrispondenze di formato:
        
          - **Cifre iniziali per i numeri che si desidera consentire:** Immettere i valori di prefisso che questa route deve contenere (incluso il + iniziale se necessario). Ad esempio, digitare **+ 425**, quindi fare clic su **Aggiungi**. Ripetere questa operazione per ogni valore di prefisso da includere nella route.
        
          - **Eccezioni:** Se si desidera specificare una o più eccezioni per un valore di prefisso, evidenziare il prefisso e fare clic su **eccezioni**. Digitare uno o più valori per i formati di corrispondenza che la route *non* deve includere. Ad esempio, per escludere i numeri che iniziano con + 425237 dalla Route, immettere il valore **+ 425237** nel campo **eccezioni** e quindi fare clic su **OK**.
    
      - Per definire manualmente il formato di corrispondenza, fare clic su **Modifica** nello strumento **Formato per corrispondenza** e quindi digitare un'espressione regolare .NET Framework per specificare il formato di corrispondenza per i numeri di telefono di destinazione ai quali viene applicata la route. Per informazioni dettagliate su come scrivere espressioni regolari, vedere la sezione relativa alle espressioni regolari di [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).NET Framework all'indirizzo.

9.  Selezionare **Ometti ID chiamante** se non si desidera che l'ID del telefono che effettua la chiamata in uscita venga visualizzato al destinatario della chiamata. Se si seleziona questa opzione, è necessario specificare un **ID chiamante alternativo** che verrà visualizzato sullo schermo dell'ID chiamante del destinatario.

10. Per associare uno o più trunk alla route vocale, fare clic su **Aggiungi** e quindi selezionare un trunk dall'elenco.
    
    <div>
    

    > [!NOTE]  
    > Se la distribuzione include tutti i Mediation Server di Microsoft Office Communications Server 2007 R2, saranno disponibili anche nell'elenco.

    
    </div>

11. Per associare uno o più utilizzi PSTN (Public Switched Telephone Network) alla route vocale, fare clic su **Seleziona** e scegliere un record nell'elenco dei record di utilizzo PSTN definiti per la distribuzione di VoIP aziendale.
    
    <div>
    

    > [!NOTE]  
    > Per visualizzare le proprietà di ognuno dei record di utilizzo PSTN disponibili, vedere <A href="lync-server-2013-view-pstn-usage-records.md">visualizzare i record di utilizzo PSTN in Lync Server 2013</A>.<BR>Per creare o modificare i record di utilizzo PSTN, vedere <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">creare un criterio vocale e configurare i record di utilizzo PSTN in Lync server 2013</A> o <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">modificare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013</A>.

    
    </div>

12. Disporre i record di utilizzo PSTN per garantire prestazioni ottimali. Per modificare la posizione di un record nell'elenco, evidenziare il nome del record e fare clic sulla freccia in su o in giù.
    
    <div>
    

    > [!NOTE]  
    > A differenza di un criterio vocale, in cui l'ordine in cui sono elencati i record di utilizzo PSTN è importante, l'ordine in cui i record di utilizzo PSTN sono elencati nella route vocale è insignificante. Tuttavia, si consiglia di organizzare l'elenco in base alla frequenza di utilizzo. Ad esempio: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Lync Server attraversa l'elenco dall'alto verso il basso).

    
    </div>

13. Digitare un valore nel campo **Numero convertito da testare** e fare clic su **Vai**. I risultati del test vengono visualizzati nel campo (facoltativo).
    
    <div>
    

    > [!NOTE]  
    > È possibile salvare una route vocale che non passa ancora il test e quindi riconfigurarla successivamente. Per ulteriori informazioni, vedere <A href="lync-server-2013-test-voice-routing.md">test Voice routing in Lync Server 2013</A>.

    
    </div>

14. Fare clic su **OK** per salvare la route vocale.

<div>


> [!IMPORTANT]  
> Ogni volta che si crea una route vocale, è necessario eseguire il comando <STRONG>Commit all</STRONG> per pubblicare la modifica della configurazione. Per ulteriori informazioni, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Modificare una route vocale in Lync Server 2013](lync-server-2013-modify-a-voice-route.md)  
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

