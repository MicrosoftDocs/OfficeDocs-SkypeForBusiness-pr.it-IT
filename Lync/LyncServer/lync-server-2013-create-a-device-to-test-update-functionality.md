---
title: 'Lync Server 2013: creare un dispositivo per testare la funzionalità di aggiornamento'
description: 'Lync Server 2013: creare un dispositivo per testare la funzionalità di aggiornamento.'
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
ms.openlocfilehash: 1d45d8970dc72abc8ea6095c879272394e34c54d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542172"
---
# <a name="create-a-device-to-test-update-functionality-in-lync-server-2013"></a>Creare un dispositivo per testare la funzionalità di aggiornamento in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

È possibile aggiungere un dispositivo di test nella pagina **Dispositivo di test** e quindi utilizzarlo per verificare le funzionalità dei nuovi aggiornamenti prima di distribuirli nei dispositivi di produzione. È possibile testare un dispositivo globalmente (nell'intero ambiente Lync Server) o all'interno di un singolo sito. Per identificare un dispositivo di test, utilizzare il relativo indirizzo MAC (Media Access Control) o il numero di serie. Quando si aggiunge un dispositivo, quest'ultimo viene visualizzato nell'elenco nella pagina **dispositivo di test** del pannello di controllo di Lync Server.

<div>

## <a name="to-add-a-test-device"></a>Per aggiungere un dispositivo di test

1.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Sulla barra di spostamento sinistra fare clic su **Client** e quindi su **Dispositivo di test**.

3.  Fare clic su **Nuovo** e quindi scegliere **Dispositivo di test globale** o **Dispositivo di test sito**.

4.  Eseguire una delle operazioni seguenti:
    
      - Se si è fatto clic su **Dispositivo di test globale**, procedere al passaggio successivo.
    
      - Se si è fatto clic su **Dispositivo di test sito**, selezionare un sito nell'elenco dei siti disponibili e quindi fare clic su **OK**.

5.  In **Nuovo dispositivo di test** digitare un nome per il dispositivo in **Nome dispositivo**.

6.  In **Tipo di identificatore** fare clic su **Indirizzo MAC** o **Numero di serie**.

7.  Nella casella **Identificatore univoco** digitare l'indirizzo MAC o il numero di serie del dispositivo.

8.  Fare clic su **Commit**.

</div>

<div>

## <a name="creating-test-devices-by-using-windows-powershell-cmdlets"></a>Creazione di dispositivi di test tramite i cmdlet di Windows PowerShell

I dispositivi di test possono essere creati utilizzando Windows PowerShell e il cmdlet New-CsTestDevice. Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

Se si creano dispositivi di test utilizzando questo cmdlet, è necessario eseguire due operazioni:

  - Specificare MACAddress o SerialNumber come IdentifierType.

  - Includere l'ambito quando si specifica l'identità (Identity) del dispositivo. Per creare un nuovo dispositivo nell'ambito globale, utilizzare una sintassi simile alla seguente:
    
        -Identity "global/WindowsPhone"
    
    Per creare un dispositivo di test nell'ambito del sito, utilizzare una sintassi simile alla seguente:
    
        -Identity "site:Redmond/WindowsPhone"

<div>

## <a name="to-create-a-test-device-by-using-the-mac-address"></a>Per creare un dispositivo di test utilizzando l'indirizzo MAC

  - Il comando seguente crea un dispositivo di test nell'ambito globale utilizzando l'indirizzo MAC come IdentifierType:
    
        New-CsTestDevice -Identity "global/WindowsPhone" -IdentifierType "MACAddress" -Identifier "01:02:03:04:05:06"

</div>

<div>

## <a name="to-create-a-test-device-by-using-the-serial-number"></a>Per creare un dispositivo di test utilizzando il numero di serie

  - Il comando seguente crea un nuovo dispositivo di test nell'ambito del sito (per il sito Redmond) e utilizza il numero di serie come IdentifierType:
    
        New-CsTestDevice -Identity "site:Redmond/WindowsPhone" -IdentifierType "SerialNumber" -Identifier "01ABC5419JKR55T"

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

