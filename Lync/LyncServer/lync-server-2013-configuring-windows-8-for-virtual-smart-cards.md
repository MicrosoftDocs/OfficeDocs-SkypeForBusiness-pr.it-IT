---
title: 'Lync Server 2013: configurazione di Windows 8 per smart card virtuali'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Windows 8 for Virtual Smart Cards
ms:assetid: 4916c167-4ee3-4f3e-b65c-33e588595112
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308564(v=OCS.15)
ms:contentKeyID: 54973684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e177e5f9786b103c086630984be849c320801a82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981126"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-windows-8-for-using-virtual-smart-cards-with-lync-server-2013"></a>Configurazione di Windows 8 per l'uso di smart card virtuali con Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-07-03_

Un fattore da tenere in considerazione quando si distribuisce l'autenticazione a due fattori e la tecnologia Smart Card è il costo di implementazione. Windows 8 offre una serie di nuove funzionalità di sicurezza e una delle nuove caratteristiche più interessanti è il supporto per le smart card virtuali.

Per i computer dotati di un chip TPM (Trusted Platform Module) che soddisfa la specifica versione 1,2, le organizzazioni possono ora ottenere i vantaggi dell'accesso tramite smart card senza apportare ulteriori investimenti nell'hardware. Per altre informazioni, vedere uso di smart card virtuali con Windows 8 [http://go.microsoft.com/fwlink/p/?LinkId=313365](http://go.microsoft.com/fwlink/p/?linkid=313365)at.

<div>

## <a name="to-configure-windows-8-for-virtual-smart-cards"></a>Per configurare Windows 8 per smart card virtuali

1.  Accedere al computer con Windows 8 usando le credenziali di un utente abilitato per Lync.

2.  Nella schermata Start di Windows 8 Posizionare il cursore nell'angolo in basso a destra dello schermo.

3.  Selezionare l'opzione di **ricerca** e quindi cercare **prompt dei comandi**.

4.  Fare clic con il pulsante destro del mouse sul **prompt dei comandi**e quindi scegliere **Esegui come amministratore**.

5.  Aprire la console di gestione TPM (Trusted Platform Module) eseguendo il comando seguente:
    
        Tpm.msc

6.  Nella console di gestione TPM verificare che la versione specifica del TPM sia di almeno 1,2
    
    <div>
    

    > [!NOTE]  
    > Se viene visualizzata una finestra di dialogo che indica che non è possibile trovare un modulo TPM (compatible Trust Platform Module), verificare che il computer disponga di un modulo TPM compatibile e che sia abilitato nel BIOS di sistema.

    
    </div>

7.  Chiudere la console di gestione TPM

8.  Dal prompt dei comandi creare una nuova smart card virtuale usando il comando seguente:
    
        TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
    
    <div>
    

    > [!NOTE]  
    > Per specificare un valore PIN personalizzato durante la creazione della smart card virtuale, usare invece il prompt di/pin.

    
    </div>

9.  Dal prompt dei comandi aprire la console di gestione computer eseguendo il comando seguente:
    
        CompMgmt.msc

10. Nella console di gestione computer selezionare **Gestione dispositivi**.

11. Espandi **lettori di smart card**.

12. Verificare che il nuovo lettore di smart card virtuale sia stato creato correttamente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

