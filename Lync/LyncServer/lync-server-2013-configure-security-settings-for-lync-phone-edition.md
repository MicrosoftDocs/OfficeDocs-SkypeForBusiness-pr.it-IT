---
title: 'Lync Server 2013: configurare le impostazioni di sicurezza per Lync Phone Edition'
description: 'Lync Server 2013: configurare le impostazioni di sicurezza per Lync Phone Edition.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure security settings for Lync Phone Edition
ms:assetid: 6e7cec17-8a79-4428-9300-8821256c46cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521014(v=OCS.15)
ms:contentKeyID: 48184464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82e6a6488db66a8497930ee6b2d1aec6fc8b0b2d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564352"
---
# <a name="configure-security-settings-for-lync-phone-edition-in-lync-server-2013"></a>Configurare le impostazioni di sicurezza per Lync Phone Edition in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

Contribuire a migliorare la sicurezza dei dispositivi che eseguono Lync Phone Edition tramite l'impostazione di sicurezza SIP e le impostazioni di blocco del telefono.

<div>

## <a name="to-configure-security-settings-for-lync-phone-edition"></a>Per configurare le impostazioni di sicurezza per Lync Phone Edition

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Client** e quindi su **Configurazione dispositivo**.

4.  Nell'elenco delle configurazioni dei dispositivi nella pagina **Configurazione dispositivo** fare doppio clic sulla configurazione per cui si desidera modificare le impostazioni di sicurezza.

5.  In **Modifica configurazione dispositivo** specificare il livello di sicurezza SIP in **Sicurezza SIP**. Il livello predefinito è **Alto**, che rappresenta anche il livello consigliabile.

6.  In **Modifica configurazione dispositivo**, sotto **Blocco telefono**, selezionare o deselezionare la casella **Applica blocco dispositivo**, selezionata per impostazione predefinita, e specificare la lunghezza minima del PIN (per impostazione predefinita, 6 caratteri), e il periodo di timeout (10 minuti, per impostazione predefinita). È consigliabile utilizzare queste impostazioni predefinite o aumentare la lunghezza del PIN e/o dimunuire il periodo di timeout.
    
    <div>
    

    > [!NOTE]  
    > Per ulteriori informazioni, vedere <A href="lync-server-2013-enforce-phone-locking.md">enforce Phone locking in Lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="configuring-security-settings-for-lync-phone-edition-phones-by-using-windows-powershell-cmdlets"></a>Configurazione delle impostazioni di sicurezza per i telefoni di Lync Phone Edition tramite i cmdlet di Windows PowerShell

È possibile gestire le impostazioni di sicurezza utilizzando Lync Server Management Shell e il cmdlet **Get-CsUCPhoneConfiguration** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-modify-the-sip-security-mode"></a>Per modificare la modalità di protezione SIP

  - Questo comando imposta su Media la modalità di protezione SIP (SIPSecurityMode) della raccolta globale di impostazioni del telefono per le comunicazioni unificate. La sicurezza SIP può essere impostata su Bassa o Avanzata (valore predefinito).
    
        Set-CsUCPhoneConfiguration -Identity global -SIPSecurityMode "Medium"

</div>

<div>

## <a name="to-modify-the-minimum-pin-length"></a>Per modificare la lunghezza minima del PIN

  - In questo esempio, tutte le impostazioni del telefono per le comunicazioni unificate sono modificate affinché richiedano una lunghezza del PIN di 7 cifre.
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -MinPhonePinLength 7

</div>

Per informazioni dettagliate, vedere [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Gestione dell'autenticazione di Lync Server 2013](lync-server-2013-managing-lync-server-authentication.md)  


[Gestione di dispositivi, telefoni e applicazioni client in Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

