---
title: 'Lync Server 2013: configurazione di Windows 8 per smart card virtuali'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Windows 8 for Virtual Smart Cards
ms:assetid: 4916c167-4ee3-4f3e-b65c-33e588595112
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308564(v=OCS.15)
ms:contentKeyID: 54973684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29fa0be32f5a2c2a0af0b63dadddda3038675adf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154078"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-windows-8-for-using-virtual-smart-cards-with-lync-server-2013"></a>Configurazione di Windows 8 per l'utilizzo di smart card virtuali con Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-07-03_

Uno dei fattori da considerare quando si distribuisce l'autenticazione a due fattori e la tecnologia Smart Card è il costo dell'implementazione. Windows 8 fornisce una serie di nuove funzionalità di sicurezza e una delle nuove funzionalità più interessanti è il supporto per le smart card virtuali.

Per i computer dotati di un chip TPM (Trusted Platform Module) che soddisfa la specifica versione 1,2, le organizzazioni possono ora ottenere i vantaggi dell'accesso tramite smart card senza effettuare ulteriori investimenti nell'hardware. Per ulteriori informazioni, vedere Using Virtual Smart Cards with Windows 8 [https://go.microsoft.com/fwlink/p/?LinkId=313365](https://go.microsoft.com/fwlink/p/?linkid=313365)at.

<div>

## <a name="to-configure-windows-8-for-virtual-smart-cards"></a>Per configurare Windows 8 per smart card virtuali

1.  Eseguire l'accesso al computer con Windows 8 utilizzando le credenziali di un utente abilitato per Lync.

2.  Nella schermata Start di Windows 8, spostare il cursore nell'angolo in basso a destra dello schermo.

3.  Selezionare l'opzione di **ricerca** e quindi cercare il **prompt dei comandi**.

4.  Fare clic con il pulsante destro del mouse su **prompt dei comandi**e quindi scegliere **Esegui come amministratore**.

5.  Aprire la console di gestione TPM (Trusted Platform Module) eseguendo il comando riportato di seguito:
    
        Tpm.msc

6.  Dalla console di gestione TPM, verificare che la versione specifica TPM sia almeno 1,2
    
    <div>
    

    > [!NOTE]  
    > Se viene visualizzata una finestra di dialogo in cui viene indicato che non è possibile trovare un modulo TPM (Trusted Trust Platform Module), verificare che il computer disponga di un modulo TPM compatibile e che sia abilitato nel BIOS del sistema.

    
    </div>

7.  Chiudere la console di gestione TPM

8.  Al prompt dei comandi creare una nuova smart card virtuale utilizzando il comando seguente:
    
        TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
    
    <div>
    

    > [!NOTE]  
    > Per fornire un valore PIN personalizzato quando si crea la smart card virtuale, utilizzare invece il prompt di/pin.

    
    </div>

9.  Al prompt dei comandi, aprire la console di gestione computer eseguendo il comando riportato di seguito:
    
        CompMgmt.msc

10. Nella console Gestione computer selezionare **Gestione dispositivi**.

11. Espandere **lettori di smart card**.

12. Verificare che il nuovo lettore di smart card virtuale sia stato creato correttamente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

