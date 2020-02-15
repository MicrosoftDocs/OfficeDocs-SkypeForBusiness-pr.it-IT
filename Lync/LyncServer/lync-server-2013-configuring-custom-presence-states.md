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
ms.openlocfilehash: 75e2e47af4951e98f21ea6b26572d39b5eebcb8d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-custom-presence-states-in-lync-server-2013"></a><span data-ttu-id="e513f-102">Configurazione degli Stati di presenza personalizzati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e513f-102">Configuring custom presence states in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e513f-103">_**Ultimo argomento modificato:** 2013-01-10_</span><span class="sxs-lookup"><span data-stu-id="e513f-103">_**Topic Last Modified:** 2013-01-10_</span></span>

<span data-ttu-id="e513f-104">Per definire stati di presenza personalizzati in Lync 2013, creare un file di configurazione della presenza personalizzato XML e quindi specificarne il percorso utilizzando i cmdlet **New-CsClientPolicy** o **Set-CsClientPolicy** di Lync Server Management Shell con il parametro CustomStateURL.</span><span class="sxs-lookup"><span data-stu-id="e513f-104">To define custom presence states in Lync 2013, create an XML custom presence configuration file, and then specify its location by using the Lync Server Management Shell cmdlets **New-CSClientPolicy** or **Set-CSClientPolicy** with the parameter CustomStateURL.</span></span>

<span data-ttu-id="e513f-105">Le proprietà dei file di configurazione sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="e513f-105">Configuration files have the following properties:</span></span>

  - <span data-ttu-id="e513f-106">Gli stati di presenza personalizzati possono essere configurati con gli indicatori di presenza Disponibile, Non disponibile e Non disturbare.</span><span class="sxs-lookup"><span data-stu-id="e513f-106">Custom presence states can be configured with the Available, Busy, and Do Not Disturb presence indicators.</span></span>

  - <span data-ttu-id="e513f-107">L'attributo di disponibilità determina quale indicatore di presenza è associato al testo dello stato personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e513f-107">The availability attribute determines which presence indicator is associated with the status text of the custom state.</span></span> <span data-ttu-id="e513f-108">Nell'esempio più avanti in questo argomento, il testo di stato che funziona da Home viene visualizzato a destra dell'indicatore di presenza verde (disponibile).</span><span class="sxs-lookup"><span data-stu-id="e513f-108">In the example later in this topic, the status text Working from Home is displayed to the right of the green (Available) presence indicator.</span></span>

  - <span data-ttu-id="e513f-109">Il testo di stato può essere composto al massimo da 64 caratteri.</span><span class="sxs-lookup"><span data-stu-id="e513f-109">The maximum length of the status text is 64 characters.</span></span>

  - <span data-ttu-id="e513f-110">È possibile aggiungere al massimo quattro stati di presenza personalizzati.</span><span class="sxs-lookup"><span data-stu-id="e513f-110">A maximum of four custom presence states can be added.</span></span>

  - <span data-ttu-id="e513f-111">Il parametro CustomStateURL consente di specificare il percorso del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="e513f-111">The CustomStateURL parameter specifies the location of the configuration file.</span></span> <span data-ttu-id="e513f-112">In Lync 2013, la modalità di protezione elevata SIP è abilitata per impostazione predefinita, pertanto sarà necessario archiviare il file di configurazione della presenza personalizzata in un server Web in cui è abilitato HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e513f-112">In Lync 2013, SIP high security mode is enabled by default, so you will need to store the custom presence configuration file on a web server that has HTTPS enabled.</span></span> <span data-ttu-id="e513f-113">In caso contrario, i client Lync 2013 non saranno in grado di connettersi.</span><span class="sxs-lookup"><span data-stu-id="e513f-113">Otherwise, Lync 2013 clients will be unable to connect to it.</span></span> <span data-ttu-id="e513f-114">Ad esempio, un indirizzo valido sarebbe `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`.</span><span class="sxs-lookup"><span data-stu-id="e513f-114">For example, a valid address would be `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e513f-115">Anche se non è consigliato in un ambiente di produzione, è possibile testare un file di configurazione che si trova in una condivisione file non HTTPS utilizzando l'impostazione del registro di sistema EnableSIPHighSecurityMode per disabilitare la modalità di sicurezza SIP sul client.</span><span class="sxs-lookup"><span data-stu-id="e513f-115">Although it is not recommended in a production environment, you can test a configuration file that is located on a non-HTTPS file share by using the EnableSIPHighSecurityMode registry setting to disable SIP high security mode on the client.</span></span> <span data-ttu-id="e513f-116">È quindi possibile utilizzare l'impostazione del registro di sistema CustomStateURL per specificare un percorso non HTTPS per il file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="e513f-116">Then you can use the CustomStateURL registry setting to specify a non-HTTPS location for the configuration file.</span></span> <span data-ttu-id="e513f-117">Si noti che Lync 2013 rispetta le impostazioni del registro di sistema di Lync 2010, ma l'hive del registro di sistema è stato aggiornato.</span><span class="sxs-lookup"><span data-stu-id="e513f-117">Note that Lync 2013 honors Lync 2010 registry settings, but the registry hive has been updated.</span></span> <span data-ttu-id="e513f-118">È necessario creare le impostazioni del registro di sistema nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="e513f-118">You would create the registry settings as follows:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="e513f-119">HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</span><span class="sxs-lookup"><span data-stu-id="e513f-119">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</span></span></P>
> <P><span data-ttu-id="e513f-120">Tipo: DWORD</span><span class="sxs-lookup"><span data-stu-id="e513f-120">Type: DWORD</span></span></P>
> <P><span data-ttu-id="e513f-121">Dati valore: 0</span><span class="sxs-lookup"><span data-stu-id="e513f-121">Value data: 0</span></span></P>
> <LI>
> <P><span data-ttu-id="e513f-122">HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</span><span class="sxs-lookup"><span data-stu-id="e513f-122">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</span></span></P>
> <P><span data-ttu-id="e513f-123">Digitare: String (REG_SZ)</span><span class="sxs-lookup"><span data-stu-id="e513f-123">Type: String (REG_SZ)</span></span></P>
> <P><span data-ttu-id="e513f-124">Dati valore (esempi): file://\\lspool. Corp. contoso. com\LSFileShare\ClientConfigFolder\Presence.xml o file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.XML</span><span class="sxs-lookup"><span data-stu-id="e513f-124">Value data (examples): file://\\lspool.corp.contoso.com\LSFileShare\ClientConfigFolder\Presence.xml or file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</span></span></P></LI></UL>



</div>

<span data-ttu-id="e513f-125">Localizzare lo stato di presenza personalizzato specificando uno o più schemi di ID impostazioni locali (LCID) nel file di configurazione XML.</span><span class="sxs-lookup"><span data-stu-id="e513f-125">Localize your custom presence state by specifying one or more locale ID (LCID) schema in the XML configuration file.</span></span> <span data-ttu-id="e513f-126">Nell'esempio riportato più avanti in questo argomento è illustrata la localizzazione in Inglese - Stati Uniti (1033), Norvegese - Bokmål (1044), Francese - Francia (1036) e Turco (1055).</span><span class="sxs-lookup"><span data-stu-id="e513f-126">The example later in this topic shows localization into English - United States (1033), Norwegian - Bokmål (1044), French - France (1036), and Turkish (1055).</span></span> <span data-ttu-id="e513f-127">Per un elenco di LCID, vedere ID delle impostazioni locali assegnati da Microsoft all' <http://go.microsoft.com/fwlink/p/?linkid=157331>indirizzo.</span><span class="sxs-lookup"><span data-stu-id="e513f-127">For a list of LCIDs, see Locale IDs Assigned by Microsoft at <http://go.microsoft.com/fwlink/p/?linkid=157331>.</span></span>

<div>

## <a name="to-add-custom-presence-states-to-lync-2013"></a><span data-ttu-id="e513f-128">Per aggiungere stati di presenza personalizzati a Lync 2013</span><span class="sxs-lookup"><span data-stu-id="e513f-128">To add custom presence states to Lync 2013</span></span>

1.  <span data-ttu-id="e513f-129">Creare un file di configurazione XML nel formato dell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="e513f-129">Create an XML configuration file that uses the format of the following example:</span></span>
    
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

2.  <span data-ttu-id="e513f-130">Salvare il file di configurazione XML in un server Web con HTTPS abilitato.</span><span class="sxs-lookup"><span data-stu-id="e513f-130">Save the XML configuration file to a web server with HTTPS enabled.</span></span> <span data-ttu-id="e513f-131">In questo esempio il file è denominato Presence. XML e salvato nel percorso https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml.</span><span class="sxs-lookup"><span data-stu-id="e513f-131">In this example, the file is named Presence.xml and saved to the location https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml.</span></span>

3.  <span data-ttu-id="e513f-132">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e513f-132">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="e513f-133">In Lync Server Management Shell, definire il percorso del file di configurazione XML utilizzando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="e513f-133">In the Lync Server Management Shell, define the location of your XML configuration file by using a command similar to the following:</span></span>
    
        New-CsClientPolicy -Identity ContosoCustomStates 
        -CustomStateURL "https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml"

5.  <span data-ttu-id="e513f-134">Utilizzare il cmdlet **Grant-CsClientPolicy** per assegnare questo nuovo criterio agli utenti.</span><span class="sxs-lookup"><span data-stu-id="e513f-134">Use the **Grant-CSClientPolicy** cmdlet to assign this new policy to users.</span></span>

<span data-ttu-id="e513f-135">Per informazioni dettagliate, vedere [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) e [Grant-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) nella documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e513f-135">For details, see [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) and [Grant-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) in the Lync Server Management Shell documentation.</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="e513f-136">Per impostazione predefinita, Lync Server&nbsp;2013 aggiorna i criteri e le impostazioni del client ogni tre ore.</span><span class="sxs-lookup"><span data-stu-id="e513f-136">By default, Lync Server 2013&nbsp;updates client policies and settings every three hours.</span></span></P>
> <LI>
> <P><span data-ttu-id="e513f-137">Se si desidera continuare a utilizzare le impostazioni di criteri di gruppo dalle versioni precedenti, ad esempio CustomStateURL, Lync 2013 riconoscerà le impostazioni se si trovano nel nuovo hive del registro di sistema di criteri (HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync).</span><span class="sxs-lookup"><span data-stu-id="e513f-137">If you want to continue using Group Policy settings from previous releases, such as CustomStateURL, Lync 2013 will recognize the settings if they are located in the new policy registry hive (HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync).</span></span> <span data-ttu-id="e513f-138">Tuttavia, i criteri dei client basati su server hanno la precedenza.</span><span class="sxs-lookup"><span data-stu-id="e513f-138">However, server-based client policies take precedence.</span></span></P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

