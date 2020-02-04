---
title: 'Lync Server 2013: creare un dispositivo per testare la funzionalità di aggiornamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a device to test update functionality
ms:assetid: ce509fd1-17b3-4b78-b269-fe5d06fe2e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182587(v=OCS.15)
ms:contentKeyID: 48185466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b197c4b42542310746568fe351f98c7d991509cf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740546"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-device-to-test-update-functionality-in-lync-server-2013"></a>Creare un dispositivo per testare la funzionalità di aggiornamento in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

È possibile aggiungere un dispositivo di test nella pagina **Dispositivo di test** e quindi usare il dispositivo per verificare le funzionalità dei nuovi aggiornamenti prima di distribuirli nei dispositivi di produzione. È possibile testare un dispositivo a livello globale (nell'intero ambiente Lync Server) o all'interno di un singolo sito. Per identificare un dispositivo di test, usare il relativo indirizzo MAC (Media Access Control) o il numero di serie. Quando si aggiunge un dispositivo, questo viene visualizzato nell'elenco nella pagina del **dispositivo di test** del pannello di controllo di Lync Server.

<div>

## <a name="to-add-a-test-device"></a>Per aggiungere un dispositivo di test

1.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Sulla barra di spostamento sinistra fare clic su **client**e quindi su **Test Device**.

3.  Fare clic su **nuovo**e quindi su dispositivo **test globale** o **dispositivo test sito**.

4.  Esegui una delle operazioni seguenti:
    
      - Se si è selezionato **dispositivo test globale**, passare al passaggio successivo.
    
      - Se si è scelto il **dispositivo di test del sito**, selezionare un sito nell'elenco dei siti disponibili e quindi fare clic su **OK**.

5.  In **nuovo dispositivo di test**Digitare un nome per il dispositivo in **nome dispositivo**.

6.  In **tipo identificatore**fare clic su **indirizzo Mac** o **numero seriale**.

7.  Nella casella **identificatore univoco** Digitare l'indirizzo Mac o il numero di serie del dispositivo.

8.  Fare clic su **Commit**.

</div>

<div>

## <a name="creating-test-devices-by-using-windows-powershell-cmdlets"></a>Creazione di dispositivi di test con i cmdlet di Windows PowerShell

I dispositivi di test possono essere creati usando Windows PowerShell e il cmdlet New-CsTestDevice. Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

Quando si creano dispositivi di test con questo cmdlet, è necessario eseguire due operazioni:

  - Specifica MACAddress o NumeroSerie come IdentifierType.

  - Includere l'ambito quando si specifica l'identità del dispositivo. Per creare un nuovo dispositivo in ambito globale, usare una sintassi simile alla seguente:
    
        -Identity "global/WindowsPhone"
    
    Per creare un dispositivo di test nell'ambito del sito, usare una sintassi simile alla seguente:
    
        -Identity "site:Redmond/WindowsPhone"

<div>

## <a name="to-create-a-test-device-by-using-the-mac-address"></a>Per creare un dispositivo di test usando l'indirizzo MAC

  - Questo comando crea un dispositivo di test nell'ambito globale e usa l'indirizzo MAC come IdentifierType:
    
        New-CsTestDevice -Identity "global/WindowsPhone" -IdentifierType "MACAddress" -Identifier "01:02:03:04:05:06"

</div>

<div>

## <a name="to-create-a-test-device-by-using-the-serial-number"></a>Per creare un dispositivo di test usando il numero seriale

  - Questo comando crea un nuovo dispositivo di test nell'ambito del sito (per il sito Redmond) e usa il numero seriale come IdentifierType:
    
        New-CsTestDevice -Identity "site:Redmond/WindowsPhone" -IdentifierType "SerialNumber" -Identifier "01ABC5419JKR55T"

</div>

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

