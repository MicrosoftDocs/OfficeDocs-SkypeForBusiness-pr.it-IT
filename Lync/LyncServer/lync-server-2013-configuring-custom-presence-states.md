---
title: 'Lync Server 2013: configurazione degli Stati di presenza personalizzati'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring custom presence states
ms:assetid: e17364a8-8b93-45fc-a614-c80e45435d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398997(v=OCS.15)
ms:contentKeyID: 48185534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12083d1895f8e5191f15b43efaf2835faecdb5ca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977676"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-custom-presence-states-in-lync-server-2013"></a>Configurazione degli Stati di presenza personalizzati in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-01-10_

Per definire gli Stati di presenza personalizzati in Lync 2013, creare un file di configurazione della presenza personalizzata XML e quindi specificarne la posizione usando i cmdlet di Lync Server Management Shell **New-CsClientPolicy** o **Set-CsClientPolicy** con il parametro CustomStateURL.

I file di configurazione hanno le proprietà seguenti:

  - Gli Stati di presenza personalizzati possono essere configurati con gli indicatori di presenza disponibile, occupato e non disturbare.

  - L'attributo Availability determina l'indicatore di presenza associato al testo dello stato personalizzato. Nell'esempio più avanti in questo argomento, il testo di stato che lavora da casa viene visualizzato a destra dell'indicatore di presenza verde (disponibile).

  - La lunghezza massima del testo di stato è di 64 caratteri.

  - È possibile aggiungere un massimo di quattro stati di presenza personalizzati.

  - Il parametro CustomStateURL specifica la posizione del file di configurazione. In Lync 2013 la modalità di protezione elevata SIP è abilitata per impostazione predefinita, quindi sarà necessario archiviare il file di configurazione della presenza personalizzato in un server Web con HTTPS abilitato. In caso contrario, i client Lync 2013 non saranno in grado di connettersi. Ad esempio, un indirizzo valido sarebbe `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`.

<div>


> [!NOTE]  
> Anche se non è consigliabile in un ambiente di produzione, è possibile testare un file di configurazione che si trova in una condivisione di file non HTTPS usando l'impostazione del registro di sistema EnableSIPHighSecurityMode per disabilitare la modalità di protezione elevata SIP nel client. Puoi quindi usare l'impostazione del registro di sistema CustomStateURL per specificare una posizione non HTTPS per il file di configurazione. Si noti che Lync 2013 rispetta le impostazioni del registro di sistema di Lync 2010, ma l'hive del registro di sistema è stato aggiornato. È necessario creare le impostazioni del registro di sistema nel modo seguente: 
> <UL>
> <LI>
> <P>HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</P>
> <P>Digitare: DWORD</P>
> <P>Dati valore: 0</P>
> <LI>
> <P>HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</P>
> <P>Digitare: String (REG_SZ)</P>
> <P>Dati valore (esempi): file://\\lspool. Corp. contoso. com\LSFileShare\ClientConfigFolder\Presence.xml o file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.XML</P></LI></UL>



</div>

Localizza lo stato di presenza personalizzato specificando uno o più schemi di ID impostazioni locali (LCID) nel file di configurazione XML. L'esempio più avanti in questo argomento Mostra la localizzazione in inglese-Stati Uniti (1033), Norvegese-Bokmål (1044), francese-Francia (1036) e turco (1055). Per un elenco di LCID, vedere ID impostazioni locali assegnati da Microsoft at <http://go.microsoft.com/fwlink/p/?linkid=157331>.

<div>

## <a name="to-add-custom-presence-states-to-lync-2013"></a>Per aggiungere stati di presenza personalizzati a Lync 2013

1.  Creare un file di configurazione XML che usa il formato dell'esempio seguente:
    
        <?xml version="1.0"?>
        <customStates xmlns="http://schemas.microsoft.com/09/2009/communicator/customStates">
          <customState ID="1" availability="online">
            <activity LCID="1033">Working from Home</activity>
            <activity LCID="1044">activity 2 for 1044</activity>
            <activity LCID="1055">activity 3 for 1055</activity>
          </customState>
          <customState ID="2" availability="busy">
            <activity LCID="1033">In a Live Meeting</activity>
            <activity LCID="1036">Equivalent French String for - In a Live Meeting </activity>
          </customState>
          <customState ID="3" availability="busy">
            <activity LCID="1033">Meeting with Customer</activity>
            <activity LCID="1055">meeting with client</activity>
            <activity LCID="1036">Equivalent French String for - Meeting with Customer</activity>
          </customState>
          <customState ID="4" availability="do-not-disturb">
            <activity LCID="1033">Interviewing</activity>
          </customState>
        </customStates>

2.  Salvare il file di configurazione XML in un server Web con HTTPS abilitato. In questo esempio, il file è denominato Presence. XML e salvato nella posizione https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml.

3.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

4.  In Lync Server Management Shell definire la posizione del file di configurazione XML usando un comando simile al seguente:
    
        New-CsClientPolicy -Identity ContosoCustomStates 
        -CustomStateURL "https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml"

5.  Usare il cmdlet **Grant-CsClientPolicy** per assegnare il nuovo criterio agli utenti.

Per informazioni dettagliate, vedere [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) e [Grant-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) nella documentazione di Lync Server Management Shell.

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>Per impostazione predefinita, Lync Server&nbsp;2013 aggiorna i criteri e le impostazioni del client ogni tre ore.</P>
> <LI>
> <P>Se si vuole continuare a usare le impostazioni dei criteri di gruppo dalle versioni precedenti, ad esempio CustomStateURL, Lync 2013 riconoscerà le impostazioni se si trovano nel nuovo hive del registro dei criteri (HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync). Tuttavia, i criteri client basati sul server hanno la precedenza.</P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

