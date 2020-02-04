---
title: 'Lync Server 2013: Esecuzione della preparazione del dominio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running domain preparation
ms:assetid: 95dab800-1f2c-4506-b36c-99986643b149
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398761(v=OCS.15)
ms:contentKeyID: 48184847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 408dea780b4136f86ffed30d199d1d0ee63d6821
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765064"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-domain-preparation-for-lync-server-2013"></a>Esecuzione della preparazione del dominio per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-04-16_

È possibile usare i cmdlet setup o Lync Server Management Shell per preparare i domini. Il cmdlet che prepara un dominio è **Enable-CsAdDomain**.

La preparazione del dominio è il passaggio finale della preparazione dei servizi di dominio Active Directory per Lync Server 2013.

<div>

## <a name="to-use-setup-to-prepare-domains"></a>Per usare la configurazione per preparare i domini

1.  Accedere a qualsiasi server del dominio come membro del gruppo Domain Admins.

2.  Nella cartella di installazione o nel supporto di Lync Server 2013 eseguire Setup. exe per avviare la distribuzione guidata di Lync Server.

3.  Fare clic su **Prepara Active Directory** e quindi attendere che venga determinato lo stato della distribuzione.

4.  Al **Passaggio 5: Preparazione del dominio corrente**, fare clic su **Esegui**.

5.  Nella pagina **preparazione dominio** fare clic su **Avanti**.

6.  Nella pagina **Esecuzione comandi in corso** cercare il messaggio **Stato attività: Completata** e quindi fare clic su **Visualizza registro**.

7.  Nella colonna **azione** espandere **domain prep**, cercare un ** \<\> ** risultato di esecuzione di successo alla fine di ogni attività per verificare che la preparazione del dominio sia stata completata correttamente, chiudere il log e quindi fare clic su **fine**.

8.  Attendere che la replica di Active Directory completi o forzi la replica a tutti i controller di dominio elencati nello snap-in siti e servizi di Active Directory per il controller di dominio radice della foresta.

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-domain"></a>Per usare i cmdlet per preparare il dominio

1.  Accedere a qualsiasi server del dominio come membro del gruppo Domain Admins.

2.  Installare i componenti di base di Lync Server nel modo seguente:
    
    1.  Nella cartella di installazione o nel supporto di Lync Server 2013 eseguire Setup. exe per avviare la distribuzione guidata di Lync Server.
    
    2.  Se viene richiesto di installare Microsoft Visual C++ ridistribuibile, fare clic su **Sì**.
    
    3.  Nella finestra di dialogo configurazione di Lync Server 2013 viene richiesto di installare i file di Lync Server. Scegliere il percorso predefinito o **passare** a una posizione a scelta e quindi fare clic su **Installa**.
    
    4.  Nella pagina Contratto di licenza selezionare **Accetto i termini del contratto di licenza**e quindi fare clic su **OK**. Il programma di installazione installa i componenti principali di Lync Server 2013.

3.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

4.  Eseguire
    
        Enable-CsAdDomain [-Domain <DomainFQDN>] 
    
    Ad esempio:
    
        Enable-CsAdDomain -Domain domain1.contoso.net 
    
    Se non specifichi il parametro Domain, il valore predefinito è il dominio locale.

5.  Verificare che la preparazione del dominio sia stata eseguita correttamente. Eseguire
    
        Get-CsAdDomain [-Domain <Domain FQDN>] [-DomainController <Domain controller FQDN>] [-GlobalCatalog <Global catalog server FQDN>] [-GlobalSettingsDomainController <Domain controller FQDN where global settings are stored>] 
    
    Ad esempio:
    
        Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
    
    <div>
    

    > [!NOTE]  
    > Il parametro GlobalSettingsDomainController consente di indicare dove sono archiviate le impostazioni globali. Se le impostazioni sono archiviate nel contenitore di sistema (tipico delle distribuzioni di aggiornamento che non hanno eseguito la migrazione delle impostazioni globali nel contenitore di configurazione), si definisce un controller di dominio nella radice della foresta di Active Directory. Se invece le impostazioni globali sono incluse nel contenitore Configuration, come avviene in genere con le distribuzioni nuove o di aggiornamento per cui è stata eseguita la migrazione delle impostazioni nel contenitore Configuration, definire un controller di dominio nella foresta. Se non specifichi questo parametro, il cmdlet presuppone che le impostazioni siano archiviate nel contenitore di configurazione e faccia riferimento a qualsiasi controller di dominio in&nbsp;Active Directory.

    
    </div>
    
    Se non specifichi il parametro **Domain** , il valore predefinito è il dominio locale.
    
    Questo cmdlet restituisce il valore di **LC\_DOMAINSETTINGS\_stato\_pronto** se la preparazione del dominio è stata completata.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Utilizzo di cmdlet per ripristinare la preparazione del dominio per Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)  


[Preparazione dei domini per Lync Server 2013](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

