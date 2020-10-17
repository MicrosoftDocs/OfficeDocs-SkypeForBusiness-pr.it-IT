---
title: 'Lync Server 2013: configurazione degli Stati di presenza personalizzati'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring custom presence states
ms:assetid: e17364a8-8b93-45fc-a614-c80e45435d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398997(v=OCS.15)
ms:contentKeyID: 48185534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd551ede7d7be7e631c229e99613cfc8baa006eb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526993"
---
# <a name="configuring-custom-presence-states-in-lync-server-2013"></a>Configurazione degli Stati di presenza personalizzati in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-01-10_

Per definire stati di presenza personalizzati in Lync 2013, creare un file di configurazione della presenza personalizzato XML e quindi specificarne il percorso utilizzando i cmdlet **New-CsClientPolicy** o **Set-CsClientPolicy** di Lync Server Management Shell con il parametro CustomStateURL.

Le proprietà dei file di configurazione sono le seguenti:

  - Gli stati di presenza personalizzati possono essere configurati con gli indicatori di presenza Disponibile, Non disponibile e Non disturbare.

  - L'attributo di disponibilità determina quale indicatore di presenza è associato al testo dello stato personalizzato. Nell'esempio più avanti in questo argomento, il testo di stato che funziona da Home viene visualizzato a destra dell'indicatore di presenza verde (disponibile).

  - Il testo di stato può essere composto al massimo da 64 caratteri.

  - È possibile aggiungere al massimo quattro stati di presenza personalizzati.

  - Il parametro CustomStateURL consente di specificare il percorso del file di configurazione. In Lync 2013, la modalità di protezione elevata SIP è abilitata per impostazione predefinita, pertanto sarà necessario archiviare il file di configurazione della presenza personalizzata in un server Web in cui è abilitato HTTPS. In caso contrario, i client Lync 2013 non saranno in grado di connettersi. Ad esempio, un indirizzo valido sarebbe `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml` .

<div>


> [!NOTE]  
> Anche se non è consigliato in un ambiente di produzione, è possibile testare un file di configurazione che si trova in una condivisione file non HTTPS utilizzando l'impostazione del registro di sistema EnableSIPHighSecurityMode per disabilitare la modalità di sicurezza SIP sul client. È quindi possibile utilizzare l'impostazione del registro di sistema CustomStateURL per specificare un percorso non HTTPS per il file di configurazione. Si noti che Lync 2013 rispetta le impostazioni del registro di sistema di Lync 2010, ma l'hive del registro di sistema è stato aggiornato. È necessario creare le impostazioni del registro di sistema nel modo seguente: 
> <UL>
> <LI>
> <P>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</P>
> <P>Digitare: DWORD</P>
> <P>Dati valore: 0</P>
> <LI>
> <P>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</P>
> <P>Digitare: String (REG_SZ)</P>
> <P>Dati valore (esempi): file:// \\lspool.corp.contoso.com\LSFileShare\ClientConfigFolder\Presence.xml o file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</P></LI></UL>



</div>

Localizzare lo stato di presenza personalizzato specificando uno o più schemi di ID impostazioni locali (LCID) nel file di configurazione XML. Nell'esempio riportato più avanti in questo argomento è illustrata la localizzazione in Inglese - Stati Uniti (1033), Norvegese - Bokmål (1044), Francese - Francia (1036) e Turco (1055). Per un elenco di LCID, vedere ID delle impostazioni locali assegnati da Microsoft all'indirizzo <https://go.microsoft.com/fwlink/p/?linkid=157331> .

<div>

## <a name="to-add-custom-presence-states-to-lync-2013"></a>Per aggiungere stati di presenza personalizzati a Lync 2013

1.  Creare un file di configurazione XML nel formato dell'esempio seguente:
    
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

2.  Salvare il file di configurazione XML in un server Web con HTTPS abilitato. In questo esempio il file è denominato Presence.xml e salvato nel percorso https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml .

3.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

4.  In Lync Server Management Shell, definire il percorso del file di configurazione XML utilizzando un comando simile al seguente:
    
        New-CsClientPolicy -Identity ContosoCustomStates 
        -CustomStateURL "https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml"

5.  Utilizzare il cmdlet **Grant-CsClientPolicy** per assegnare questo nuovo criterio agli utenti.

Per informazioni dettagliate, vedere [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) e [Grant-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) nella documentazione di Lync Server Management Shell.

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>Per impostazione predefinita, Lync Server 2013 &nbsp; Aggiorna i criteri e le impostazioni del client ogni tre ore.</P>
> <LI>
> <P>Se si desidera continuare a utilizzare le impostazioni di criteri di gruppo dalle versioni precedenti, ad esempio CustomStateURL, Lync 2013 riconoscerà le impostazioni se si trovano nel nuovo hive del registro di sistema di criteri (HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync). Tuttavia, i criteri dei client basati su server hanno la precedenza.</P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

