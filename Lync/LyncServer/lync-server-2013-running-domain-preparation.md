---
title: 'Lync Server 2013: esecuzione della preparazione del dominio'
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
ms.openlocfilehash: 9cf14c4b566d6c6447776d3251004f5d508220e3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511113"
---
# <a name="running-domain-preparation-for-lync-server-2013"></a>Esecuzione della preparazione del dominio per Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-04-16_

È possibile utilizzare i cmdlet setup o Lync Server Management Shell per preparare i domini. Il cmdlet che prepara un dominio è **Enable-CsAdDomain**.

La preparazione del dominio è il passaggio finale nella preparazione di servizi di dominio Active Directory per Lync Server 2013.

<div>

## <a name="to-use-setup-to-prepare-domains"></a>Per utilizzare il programma di installazione per preparare i domini

1.  Eseguire l'accesso a un server del dominio come membro del gruppo Domain Admins.

2.  Dalla cartella o dal supporto di installazione di Lync Server 2013, eseguire Setup.exe per avviare la distribuzione guidata di Lync Server.

3.  Fare clic su **Prepara Active Directory** e quindi attendere che venga determinato lo stato della distribuzione.

4.  Al **Passaggio 5: Preparazione del dominio corrente**, fare clic su **Esegui**.

5.  Nella pagina **Prepara dominio** fare clic su **Avanti**.

6.  Nella pagina **Esecuzione comandi in corso** ricercare **Stato attività: Operazione completata** e quindi fare clic su **Visualizza registro**.

7.  Nella colonna **azione** espandere **preparazione dominio**, cercare il **\<Success\>** risultato dell'esecuzione alla fine di ogni attività per verificare che la preparazione del dominio sia stata completata correttamente, chiudere il registro e quindi fare clic su **fine**.

8.  Attendere che la replica di Active Directory venga completata o forzare la replica in tutti i controller di dominio elencati nello snap-in siti e servizi di Active Directory per il controller di dominio radice della foresta.

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-domain"></a>Per utilizzare i cmdlet per preparare il dominio

1.  Eseguire l'accesso a un server del dominio come membro del gruppo Domain Admins.

2.  Installare i componenti di base di Lync Server come indicato di seguito:
    
    1.  Dalla cartella o dal supporto di installazione di Lync Server 2013, eseguire Setup.exe per avviare la distribuzione guidata di Lync Server.
    
    2.  Se viene chiesto di installare Microsoft Visual C++ Redistributable, fare clic su **Sì**.
    
    3.  Nella finestra di dialogo installazione di Lync Server 2013 viene visualizzata una richiesta di installazione dei file di Lync Server. Scegliere il percorso predefinito o **Sfoglia** per selezionare il percorso desiderato e quindi fare clic su **Installa**.
    
    4.  Nella pagina Contratto di Licenza selezionare **Accetto i termini del Contratto di Licenza** e quindi fare clic su **OK**. Il programma di installazione installa i componenti di base di Lync Server 2013.

3.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

4.  Eseguire: 
    
        Enable-CsAdDomain [-Domain <DomainFQDN>] 
    
    Ad esempio:
    
        Enable-CsAdDomain -Domain domain1.contoso.net 
    
    Se non si specifica il parametro Domain, per impostazione predefinita verrà utilizzato il dominio locale.

5.  Verificare che la preparazione del dominio abbia avuto esito positivo. Eseguire: 
    
        Get-CsAdDomain [-Domain <Domain FQDN>] [-DomainController <Domain controller FQDN>] [-GlobalCatalog <Global catalog server FQDN>] [-GlobalSettingsDomainController <Domain controller FQDN where global settings are stored>] 
    
    Ad esempio:
    
        Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
    
    <div>
    

    > [!NOTE]  
    > Il parametro GlobalSettingsDomainController consente di indicare dove vengono archiviate le impostazioni globali. Se le impostazioni vengono archiviate nel contenitore di sistema (tipica delle distribuzioni di aggiornamento che non hanno eseguito la migrazione delle impostazioni globali nel contenitore di configurazione), è necessario definire un controller di dominio nella radice della foresta di Active Directory. Se invece le impostazioni globali sono incluse nel contenitore Configuration, come avviene in genere con le distribuzioni nuove o di aggiornamento per cui è stata eseguita la migrazione delle impostazioni nel contenitore Configuration, definire un controller di dominio nella foresta. Se non si specifica questo parametro, il cmdlet presuppone che le impostazioni siano archiviate nel contenitore di configurazione e si riferisca a qualsiasi controller di dominio in AD &nbsp; DS.

    
    </div>
    
    Se non si specifica il parametro **Domain** , il valore predefinito è il dominio locale.
    
    Questo cmdlet restituisce un valore di ** \_ stato LC \_ DOMAINSETTINGS \_ pronto** se la preparazione del dominio ha avuto esito positivo.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Utilizzo dei cmdlet per annullare la preparazione del dominio per Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)  


[Preparazione dei domini per Lync Server 2013](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

