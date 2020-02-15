---
title: 'Lync Server 2013: creare o modificare un intervallo di numeri non assegnati'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an unassigned number range
ms:assetid: a102b226-0460-4d5c-82f9-79b8444fa958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412748(v=OCS.15)
ms:contentKeyID: 48185013
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b9f35157b4172376cdcb4724346dc7cd9ecbcf0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "41994071"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-unassigned-number-range-in-lync-server-2013"></a>Creare o modificare un intervallo di numeri non assegnati in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Utilizzare una delle procedure seguenti per configurare gli intervalli di numeri non assegnati per l'applicazione annuncio.

<div>


> [!IMPORTANT]  
> Prima di configurare la tabella dei numeri non assegnati è necessario che sia definito almeno un annuncio o che sia impostato un Operatore automatico messaggistica unificata di Exchange.



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-configure-unassigned-phone-numbers"></a>Per utilizzare il pannello di controllo di Lync Server per configurare i numeri di telefono non assegnati

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Funzionalità vocali** e quindi su **Numero non assegnato**.

4.  Nella pagina **Numero non assegnato** eseguire una delle operazioni seguenti:
    
      - Per creare un nuovo intervallo di numeri, fare clic su **Nuovo**. In **Nome** digitare un nome che identifichi l'intervallo di numeri.
        
        <div>
        

        > [!NOTE]  
        > Dopo l'esecuzione del commit del nuovo intervallo di numeri non assegnati nel database non sarà possibile modificare il nome.

        
        </div>
    
      - Per modificare un intervallo di numeri esistente, digitare tutto o una parte del nome dell'intervallo di numeri nel campo di ricerca. Nell'elenco di intervalli di numeri risultante fare clic sul nome desiderato, su **Modifica** e quindi su **Mostra dettagli**.

5.  Nel primo campo **Intervallo numeri** digitare il numero iniziale dell'intervallo e nel secondo campo **Intervallo numeri** digitare il numero finale.
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P>Il numero iniziale dell'intervallo deve essere minore o uguale al numero finale dell'intervallo stesso.</P>
    > <LI>
    > <P>Se il numero iniziale o il numero finale dell'intervallo include un numero di interno, devono includerlo entrambi. Il numero di interno deve essere lo stesso per ambedue.</P>
    > <LI>
    > <P>Il numero deve corrispondere all'espressione regolare (Tel:)? \+)? [1-9] \d{0,17}(; EXT = [1-9] \d{0,9})?. Ciò significa che il numero può iniziare con la stringa tel: (se questa non viene specificata, verrà aggiunta automaticamente), un segno più (+) e una cifra compresa tra 1 e 9. Il numero di telefono può contenere fino a 17 cifre e può essere seguito da un interno nel formato ;ext= seguito dal numero dell'interno.</P></LI></UL>

    
    </div>

6.  In **Servizio Annuncio** eseguire una delle operazioni seguenti:
    
      - Fare clic su **Annuncio**.
    
      - Fare clic su **Messaggistica unificata di Exchange**.

7.  Se nel passaggio precedente è stato selezionato **Annuncio**, eseguire le operazioni seguenti:
    
    1.  In **FQDN del server di destinazione** fare clic su **Seleziona**, sull'ID del servizio applicazione che esegue l'applicazione Annuncio che gestirà le chiamate in arrivo per questo intervallo di numeri non assegnati e quindi su **OK**.
    
    2.  In **Annuncio** fare clic sull'annuncio da riprodurre per questo intervallo di numeri non assegnati.

8.  Se nel passaggio precedente si è fatto clic su **Messaggistica unificata di Exchange**, in **Numero di telefono operatore automatico** fare clic su **Seleziona**, quindi sul numero di telefono da utilizzare per l'intervallo di numeri non assegnati e quindi fare clic su **OK**.

9.  Fare clic su **OK**.

10. Nella pagina **Numero non assegnato** verificare che gli intervalli di numeri non assegnati siano disposti nell'ordine desiderato. Per modificare la posizione di un intervallo nella tabella, fare clic su uno o più nomi consecutivi nell'elenco di intervalli e quindi fare clic sulla freccia in su o sulla freccia in giù.
    
    <div>
    

    > [!TIP]  
    > Lync Server esegue la ricerca nella tabella dei numeri non assegnati dall'alto verso il basso e utilizza il primo intervallo che corrisponde al numero non assegnato. Se vi sono intervalli che si sovrappongono e per un intervallo è specificata un'azione da eseguire come ultimo tentativo, verificare che tale intervallo si trovi alla fine dell'elenco.

    
    </div>

11. Quando gli intervalli di numeri non assegnati si trovano nell'ordine desiderato, fare clic su **Salva tutto**.

</div>

<div>

## <a name="to-use-windows-powershell-to-configure-unassigned-phone-numbers"></a>Per utilizzare Windows PowerShell per configurare i numeri di telefono non assegnati

1.  Accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in [delegate Setup Permissions in Lync server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Utilizzare **New-CsUnassignedNumber** per creare un nuovo intervallo di numeri non assegnati. Utilizzare **Set-CsUnassignedNumber** per modificare un intervallo di numeri non assegnati esistente.
    
    <div>
    

    > [!TIP]  
    > Se vi sono intervalli che si sovrappongono e si desidera che gli intervalli vengano applicati in un ordine specifico, includere il parametro Priority. Alla chiamata verrà applicato l'intervallo con la priorità più alta.

    
    </div>
    
    Nella riga di comando eseguire una delle operazioni seguenti:
    
      - Per creare un intervallo di numeri per un servizio Annuncio, eseguire quanto segue:
        
            New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
    
      - Per creare un intervallo di numeri per l'Operatore automatico messaggistica unificata di Exchange, eseguire quanto segue:
        
            New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
    
    Ad esempio:
    
        New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
    
    Oppure
    
        New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
    
    Nell'esempio seguente viene illustrato come modificare i numeri di un intervallo di numeri non assegnati esistente:
    
        Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Eliminare un intervallo di numeri non assegnati in Lync Server 2013](lync-server-2013-delete-an-unassigned-number-range.md)  


[New-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/New-CsUnassignedNumber)  
[Set-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/Set-CsUnassignedNumber)  
[Get-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/Get-CsUnassignedNumber)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

