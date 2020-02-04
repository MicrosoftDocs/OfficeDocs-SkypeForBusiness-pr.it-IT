---
title: 'Lync Server 2013: amministrazione del servizio Rubrica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administering the Address Book Service
ms:assetid: 801e4243-9670-4477-aa2f-88b61ecf5351
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429711(v=OCS.15)
ms:contentKeyID: 48184649
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d12b904cbb679b66579c7c669ba46e0d732034b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administering-the-address-book-service-in-lync-server-2013"></a><span data-ttu-id="f6fe8-102">Amministrazione del servizio Rubrica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6fe8-102">Administering the Address Book Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6fe8-103">_**Argomento Ultima modifica:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="f6fe8-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="f6fe8-104">Come parte della distribuzione di Lync Server, Enterprise Edition o Standard Edition Server, il servizio Rubrica viene installato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-104">As a part of the deployment of Lync Server, Enterprise Edition or Standard Edition server, the Address Book Service is installed by default.</span></span> <span data-ttu-id="f6fe8-105">Il database usato dal servizio Rubrica-RTCab-viene creato in SQL Server (per Enterprise Edition, questo è il server SQL back-end; per il server Standard Edition, il server SQL collocato).</span><span class="sxs-lookup"><span data-stu-id="f6fe8-105">The database used by the Address Book Service – RTCab – is created on the SQL Server (for Enterprise Edition, this is the back-end SQL Server; for Standard Edition server, the collocated SQL Server).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f6fe8-106">Per informazioni sull'uso di <STRONG>ADSI Edit</STRONG> per modificare gli attributi degli oggetti dei servizi di dominio Active Directory, vedere <A href="http://go.microsoft.com/fwlink/?linkid=330427">Modifica ADSI</A>.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-106">For information about using <STRONG>ADSI Edit</STRONG> to edit Active Directory Domain Services object attributes, see <A href="http://go.microsoft.com/fwlink/?linkid=330427">ADSI Edit</A>.</span></span> <span data-ttu-id="f6fe8-107">Per informazioni su uno strumento nel Resource Kit specifico per il servizio Rubrica, vedere strumenti del <A href="http://go.microsoft.com/fwlink/?linkid=330429">Resource Kit di Microsoft Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-107">For information about a tool in the Resource Kit specifically for the Address Book service, see <A href="http://go.microsoft.com/fwlink/?linkid=330429">Microsoft Lync Server 2013 Resource Kit Tools</A>.</span></span>



</div>

<div>

## <a name="address-book-server-phone-number-normalization"></a><span data-ttu-id="f6fe8-108">Normalizzazione numero di telefono del server rubrica</span><span class="sxs-lookup"><span data-stu-id="f6fe8-108">Address Book Server Phone Number Normalization</span></span>

<span data-ttu-id="f6fe8-109">Lync Server richiede numeri di telefono RFC 3966/E. 164 standardizzati.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-109">Lync Server requires standardized RFC 3966/E.164 phone numbers.</span></span> <span data-ttu-id="f6fe8-110">Per usare numeri di telefono non strutturati o formattati in modo incoerente, Lync Server si basa sul server della Rubrica per preelaborare i numeri di telefono prima che vengano consegnati alle regole di normalizzazione.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-110">To use phone numbers that are unstructured or inconsistently formatted, Lync Server relies on the Address Book Server to preprocess phone numbers before they are handed off to the normalization rules.</span></span> <span data-ttu-id="f6fe8-111">Quando viene usato un numero di telefono dalla Rubrica e viene applicata la regola di normalizzazione, i client, ad esempio Lync Phone Edition e Lync mobile, possono usare questi numeri normalizzati.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-111">When a phone number is used from the address book and the normalization rule is applied, clients, such as Lync Phone Edition and Lync Mobile, can use these normalized numbers.</span></span>

<span data-ttu-id="f6fe8-112">Le regole di normalizzazione usate nelle versioni precedenti potrebbero non funzionare correttamente senza alcune modifiche.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-112">The normalization rules that were used in previous versions may not work properly without some adjustments.</span></span> <span data-ttu-id="f6fe8-113">Poiché gli spazi vuoti e i caratteri non obbligatori vengono rimossi prima delle regole di normalizzazione, se l'espressione Regex Cerca specificamente un trattino o un altro carattere rimosso, la regola di normalizzazione potrebbe non riuscire.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-113">Because the white space and non-mandatory characters are removed prior to the normalization rules, if your regex expression is specifically looking for a dash or other character that was removed, your normalization rule might fail.</span></span> <span data-ttu-id="f6fe8-114">È necessario rivedere le regole di normalizzazione per verificare che non siano alla ricerca di questi caratteri non obbligatori oppure che la regola non venga eseguita correttamente e che il carattere non sia presente in cui la regola lo prevede.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-114">You should review your normalization rules to ensure that either they are not looking for these non-mandatory characters, or that the rule can fail gracefully and continue in the event that the character is not present where the rule anticipates it will be.</span></span>

</div>

<div>

## <a name="user-replicator-and-address-book-server"></a><span data-ttu-id="f6fe8-115">Server di replica utenti e Rubrica</span><span class="sxs-lookup"><span data-stu-id="f6fe8-115">User Replicator and Address Book Server</span></span>

<span data-ttu-id="f6fe8-116">Il server rubrica usa i dati forniti da User Replicator per aggiornare le informazioni ottenute inizialmente dall'elenco indirizzi globale (GAL).</span><span class="sxs-lookup"><span data-stu-id="f6fe8-116">The Address Book Server uses data provided by User Replicator to update the information that it initially obtains from the global address list (GAL).</span></span> <span data-ttu-id="f6fe8-117">User Replicator scrive gli attributi dei servizi di dominio Active Directory per ogni utente, contatto e gruppo nella tabella AbUserEntry del database e il server della rubrica sincronizza i dati utente del database in file nell'archivio file della Rubrica e nel database della rubrica RTCab.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-117">User Replicator writes the Active Directory Domain Services attributes for each user, contact, and group into the AbUserEntry table in the database and the Address Book Server syncs the user data from the database into files in the Address Book Server file store and into the Address Book database RTCab.</span></span> <span data-ttu-id="f6fe8-118">Lo schema per la tabella AbUserEntry usa due colonne, **UserGuid** e **UserData**.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-118">The schema for the AbUserEntry table uses two columns, **UserGuid** and **UserData**.</span></span> <span data-ttu-id="f6fe8-119">**UserGuid** è la colonna index e contiene il GUID a 16 byte dell'oggetto Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-119">**UserGuid** is the index column and contains the 16-byte GUID of the Active Directory object.</span></span> <span data-ttu-id="f6fe8-120">**UserData** è una colonna di immagini che contiene tutti gli attributi di servizi di dominio Active Directory menzionati in precedenza per il contatto.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-120">**UserData** is an image column which contains all of the previously mentioned Active Directory Domain Services attributes for that contact.</span></span>

<span data-ttu-id="f6fe8-121">User Replicator determina gli attributi di Active Directory da scrivere leggendo una tabella di configurazione situata nella stessa istanza basata su SQL Server della tabella AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-121">User Replicator determines which Active Directory attributes to write by reading a configuration table located in the same SQL Server-based instance as the AbUserEntry table.</span></span> <span data-ttu-id="f6fe8-122">La tabella AbAttribute contiene tre colonne, **ID**, **Name**, **Flags**e **Enable**.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-122">The AbAttribute table contains three columns, **ID**, **Name**, **Flags**, and **Enable**.</span></span> <span data-ttu-id="f6fe8-123">La tabella viene creata durante la configurazione del database.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-123">The table is created during database setup.</span></span> <span data-ttu-id="f6fe8-124">Se la tabella AbAttribute è vuota, User Replicator ignora la logica di elaborazione della tabella AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-124">If the AbAttribute table is empty, User Replicator skips its AbUserEntry table processing logic.</span></span> <span data-ttu-id="f6fe8-125">Gli attributi del server della Rubrica sono dinamici e vengono recuperati dalla tabella AbAttribute, che inizialmente viene scritta dal server della Rubrica quando il server della Rubrica viene attivato.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-125">Address Book Server attributes are dynamic and are retrieved from the AbAttribute table, which is initially written by the Address Book Server when the Address Book Server is activated.</span></span>

<span data-ttu-id="f6fe8-126">L'attivazione del server rubrica viene popolata dalla tabella AbAttribute con i valori visualizzati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-126">Address Book Server activation populates the AbAttribute table with the values shown in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f6fe8-127">ID</span><span class="sxs-lookup"><span data-stu-id="f6fe8-127">ID</span></span></th>
<th><span data-ttu-id="f6fe8-128">Nome</span><span class="sxs-lookup"><span data-stu-id="f6fe8-128">Name</span></span></th>
<th><span data-ttu-id="f6fe8-129">Flag</span><span class="sxs-lookup"><span data-stu-id="f6fe8-129">Flags</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f6fe8-130">1</span><span class="sxs-lookup"><span data-stu-id="f6fe8-130">1</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-131">givenName</span><span class="sxs-lookup"><span data-stu-id="f6fe8-131">givenName</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-132">0x01400000</span><span class="sxs-lookup"><span data-stu-id="f6fe8-132">0x01400000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6fe8-133">2</span><span class="sxs-lookup"><span data-stu-id="f6fe8-133">2</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-134">Sn</span><span class="sxs-lookup"><span data-stu-id="f6fe8-134">Sn</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-135">0x02400000</span><span class="sxs-lookup"><span data-stu-id="f6fe8-135">0x02400000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6fe8-136">3</span><span class="sxs-lookup"><span data-stu-id="f6fe8-136">3</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-137">displayName</span><span class="sxs-lookup"><span data-stu-id="f6fe8-137">displayName</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-138">0x03420000</span><span class="sxs-lookup"><span data-stu-id="f6fe8-138">0x03420000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6fe8-139">4</span><span class="sxs-lookup"><span data-stu-id="f6fe8-139">4</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-140">Titolo</span><span class="sxs-lookup"><span data-stu-id="f6fe8-140">Title</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-141">0x04000000</span><span class="sxs-lookup"><span data-stu-id="f6fe8-141">0x04000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6fe8-142">5</span><span class="sxs-lookup"><span data-stu-id="f6fe8-142">5</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-143">mailNickname</span><span class="sxs-lookup"><span data-stu-id="f6fe8-143">mailNickname</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-144">0x05400000</span><span class="sxs-lookup"><span data-stu-id="f6fe8-144">0x05400000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6fe8-145">6</span><span class="sxs-lookup"><span data-stu-id="f6fe8-145">6</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-146">Società</span><span class="sxs-lookup"><span data-stu-id="f6fe8-146">Company</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-147">0x06000000</span><span class="sxs-lookup"><span data-stu-id="f6fe8-147">0x06000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6fe8-148">7</span><span class="sxs-lookup"><span data-stu-id="f6fe8-148">7</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-149">physicalDeliveryOfficeName</span><span class="sxs-lookup"><span data-stu-id="f6fe8-149">physicalDeliveryOfficeName</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-150">0x07000000</span><span class="sxs-lookup"><span data-stu-id="f6fe8-150">0x07000000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6fe8-151">8</span><span class="sxs-lookup"><span data-stu-id="f6fe8-151">8</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-152">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="f6fe8-152">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-153">0x08520C00</span><span class="sxs-lookup"><span data-stu-id="f6fe8-153">0x08520C00</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6fe8-154">9</span><span class="sxs-lookup"><span data-stu-id="f6fe8-154">9</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-155">telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="f6fe8-155">telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-156">0x09022800</span><span class="sxs-lookup"><span data-stu-id="f6fe8-156">0x09022800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6fe8-157">10</span><span class="sxs-lookup"><span data-stu-id="f6fe8-157">10</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-158">homePhone</span><span class="sxs-lookup"><span data-stu-id="f6fe8-158">homePhone</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-159">0x0A302800</span><span class="sxs-lookup"><span data-stu-id="f6fe8-159">0x0A302800</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6fe8-160">11</span><span class="sxs-lookup"><span data-stu-id="f6fe8-160">11</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-161">Dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="f6fe8-161">Mobile</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-162">0x0B622800</span><span class="sxs-lookup"><span data-stu-id="f6fe8-162">0x0B622800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6fe8-163">12</span><span class="sxs-lookup"><span data-stu-id="f6fe8-163">12</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-164">otherTelephone</span><span class="sxs-lookup"><span data-stu-id="f6fe8-164">otherTelephone</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-165">0x0C302000</span><span class="sxs-lookup"><span data-stu-id="f6fe8-165">0x0C302000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6fe8-166">13</span><span class="sxs-lookup"><span data-stu-id="f6fe8-166">13</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-167">ipPhone</span><span class="sxs-lookup"><span data-stu-id="f6fe8-167">ipPhone</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-168">0x0D302000</span><span class="sxs-lookup"><span data-stu-id="f6fe8-168">0x0D302000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6fe8-169">14</span><span class="sxs-lookup"><span data-stu-id="f6fe8-169">14</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-170">Posta</span><span class="sxs-lookup"><span data-stu-id="f6fe8-170">Mail</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-171">0x0E500000</span><span class="sxs-lookup"><span data-stu-id="f6fe8-171">0x0E500000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6fe8-172">15</span><span class="sxs-lookup"><span data-stu-id="f6fe8-172">15</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-173">groupType</span><span class="sxs-lookup"><span data-stu-id="f6fe8-173">groupType</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-174">0x0F010800</span><span class="sxs-lookup"><span data-stu-id="f6fe8-174">0x0F010800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6fe8-175">16</span><span class="sxs-lookup"><span data-stu-id="f6fe8-175">16</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-176">Dipartimento</span><span class="sxs-lookup"><span data-stu-id="f6fe8-176">Department</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-177">0x10000000</span><span class="sxs-lookup"><span data-stu-id="f6fe8-177">0x10000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6fe8-178">17</span><span class="sxs-lookup"><span data-stu-id="f6fe8-178">17</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-179">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f6fe8-179">Description</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-180">0x11000100</span><span class="sxs-lookup"><span data-stu-id="f6fe8-180">0x11000100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6fe8-181">18</span><span class="sxs-lookup"><span data-stu-id="f6fe8-181">18</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-182">Manager</span><span class="sxs-lookup"><span data-stu-id="f6fe8-182">Manager</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-183">0x12040001</span><span class="sxs-lookup"><span data-stu-id="f6fe8-183">0x12040001</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6fe8-184">19</span><span class="sxs-lookup"><span data-stu-id="f6fe8-184">19</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-185">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="f6fe8-185">proxyAddress</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-186">0x00500105</span><span class="sxs-lookup"><span data-stu-id="f6fe8-186">0x00500105</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6fe8-187">20</span><span class="sxs-lookup"><span data-stu-id="f6fe8-187">20</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-188">msExchHideFromAddressLists</span><span class="sxs-lookup"><span data-stu-id="f6fe8-188">msExchHideFromAddressLists</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-189">0xFF000003</span><span class="sxs-lookup"><span data-stu-id="f6fe8-189">0xFF000003</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6fe8-190">99</span><span class="sxs-lookup"><span data-stu-id="f6fe8-190">99</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-191">entryID</span><span class="sxs-lookup"><span data-stu-id="f6fe8-191">entryID</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-192">0x99000000</span><span class="sxs-lookup"><span data-stu-id="f6fe8-192">0x99000000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f6fe8-193">I numeri nella colonna **ID** devono essere univoci e non devono mai essere riutilizzati.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-193">The numbers in the **ID** column must be unique and should never be reused.</span></span> <span data-ttu-id="f6fe8-194">Inoltre, il mantenimento dei valori ID in 256 consente di risparmiare spazio nei file di output scritti dal server rubrica.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-194">Also, keeping the ID values under 256 saves space in the output files written by the Address Book Server.</span></span> <span data-ttu-id="f6fe8-195">Tuttavia, il valore ID massimo è 65535.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-195">However, the maximum ID value is 65535.</span></span> <span data-ttu-id="f6fe8-196">La colonna **Name** corrisponde al nome dell'attributo Active Directory che User Replicator deve inserire nella tabella AbUserEntry per ogni contatto.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-196">The **Name** column corresponds to the Active Directory attribute name that User Replicator should put in the AbUserEntry table for each contact.</span></span> <span data-ttu-id="f6fe8-197">Il valore nella colonna **Flags** viene usato per definire il tipo di attributo.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-197">The value in the **Flags** column is used to define the type of attribute.</span></span> <span data-ttu-id="f6fe8-198">I seguenti tipi di attributi del server della Rubrica sono riconosciuti da User Replicator, indicato dal byte basso del valore nella colonna **Contrassegni** .</span><span class="sxs-lookup"><span data-stu-id="f6fe8-198">The following types of Address Book Server attributes are recognized by User Replicator, indicated by the low byte of the value in the **Flags** column.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f6fe8-199">Attributo</span><span class="sxs-lookup"><span data-stu-id="f6fe8-199">Attribute</span></span></th>
<th><span data-ttu-id="f6fe8-200">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f6fe8-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f6fe8-201">0x0</span><span class="sxs-lookup"><span data-stu-id="f6fe8-201">0x0</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-202">Un attributo String.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-202">A string attribute.</span></span> <span data-ttu-id="f6fe8-203">User Replicator converte questo tipo in UTF-8 prima di archiviarlo nella tabella AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-203">User Replicator converts this type to UTF-8 before storing it in the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6fe8-204">0x1</span><span class="sxs-lookup"><span data-stu-id="f6fe8-204">0x1</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-205">Un attributo binario.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-205">A binary attribute.</span></span> <span data-ttu-id="f6fe8-206">User Replicator archivia questo contenuto nel BLOB senza alcuna conversione.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-206">User Replicator stores this in the blob without any conversion.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6fe8-207">0x2</span><span class="sxs-lookup"><span data-stu-id="f6fe8-207">0x2</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-208">Un attributo String, ma è incluso solo se il valore dell'attributo inizia &quot;con Tel&quot;:.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-208">A string attribute, but is included only if the attribute value begins with &quot;tel:&quot;.</span></span> <span data-ttu-id="f6fe8-209">Questo vale principalmente per gli attributi di stringa multivalore, in particolare <strong>proxyAddresses</strong>.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-209">This is primarily for multi-valued string attributes, specifically <strong>proxyAddresses</strong>.</span></span> <span data-ttu-id="f6fe8-210">In questo caso, il server della Rubrica è interessato solo alle voci di <strong>proxyAddresses</strong> che &quot;iniziano con&quot;Tel:.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-210">In this case, Address Book Server is interested only in <strong>proxyAddresses</strong> entries that begin with &quot;tel:&quot;.</span></span> <span data-ttu-id="f6fe8-211">Pertanto, nell'interesse del salvataggio dello spazio, User Replicator archivia solo le voci che iniziano con &quot;Tel:&quot;.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-211">Therefore, in the interest of saving space, User Replicator stores only the entries that begin with &quot;tel:&quot;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6fe8-212">0x3</span><span class="sxs-lookup"><span data-stu-id="f6fe8-212">0x3</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-213">Un attributo stringa booleano, che se TRUE fa in modo che User Replicator non includa questo contatto nella tabella AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-213">A Boolean string attribute, which if TRUE causes User Replicator to not include this contact in the AbUserEntry table.</span></span> <span data-ttu-id="f6fe8-214">Se FALSE, fa sì che User Replicator includa gli attributi per il contatto nella tabella AbUserEntry, ma non l'attributo specifico con questo contrassegno.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-214">If FALSE, it causes User Replicator to include the attributes for this contact in the AbUserEntry table, but not the particular attribute with this flag.</span></span> <span data-ttu-id="f6fe8-215">Si tratta di un altro tipo di caso speciale principalmente per l'attributo <strong>msExchHideFromAddressLists</strong> .</span><span class="sxs-lookup"><span data-stu-id="f6fe8-215">This is another special case type that is primarily for the <strong>msExchHideFromAddressLists</strong> attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6fe8-216">0x4</span><span class="sxs-lookup"><span data-stu-id="f6fe8-216">0x4</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-217">Un attributo stringa, ma è incluso solo se il valore dell'attributo inizia &quot;con SMTP&quot; : e include &quot; @ &quot; il simbolo.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-217">A string attribute, but is included only if the attribute value begins with &quot;smtp:&quot; and includes the &quot;@&quot; symbol.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6fe8-218">0x5</span><span class="sxs-lookup"><span data-stu-id="f6fe8-218">0x5</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-219">Un attributo String, ma è incluso solo se il valore dell'attributo inizia con &quot;Tel:&quot; o &quot;SMTP:&quot; e include il &quot; @ &quot; simbolo.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-219">A string attribute, but is included only if the attribute value begins with either &quot;tel:&quot; or &quot;smtp:&quot; and includes the &quot;@&quot; symbol.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6fe8-220">0x100</span><span class="sxs-lookup"><span data-stu-id="f6fe8-220">0x100</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-221">Se impostato, si tratta di un attributo multivalore che può essere visualizzato più volte per ogni contatto.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-221">If set, this is a multi-valued attribute that can appear more than once for each contact.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6fe8-222">0x400</span><span class="sxs-lookup"><span data-stu-id="f6fe8-222">0x400</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-223">Se impostato, identifica l'attributo del nome dell'account utente di posta elettronica per un contatto.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-223">If set, this identifies the email user account name attribute for a contact.</span></span> <span data-ttu-id="f6fe8-224">Il server della rubrica usa questo contrassegno per identificare il valore di attributo da visualizzare nella voce del log eventi di normalizzazione del telefono.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-224">Address Book Server uses this flag to identify which attribute value to show in the phone normalization event log entry.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6fe8-225">0x800</span><span class="sxs-lookup"><span data-stu-id="f6fe8-225">0x800</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-226">Se impostato, identifica un attributo obbligatorio per un contatto.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-226">If set, this identifies a required attribute for a contact.</span></span> <span data-ttu-id="f6fe8-227">Il server rubrica include un utente nella tabella AbUserEntry solo se è presente un valore per questo attributo in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-227">Address Book Server includes a user in the AbUserEntry table only if there is a value for this attribute in Active Directory.</span></span> <span data-ttu-id="f6fe8-228">Se è presente più di un attributo obbligatorio, è necessario che solo uno di essi abbia un valore per includere l'utente nella tabella AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-228">If there is more than one required attribute, only one of them is required to have a value to include the user in the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6fe8-229">0x1000</span><span class="sxs-lookup"><span data-stu-id="f6fe8-229">0x1000</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-230">Se impostato, il server della rubrica normalizza sempre il valore di questo attributo.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-230">If set, Address Book Server always normalizes the value of this attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6fe8-231">0x2000</span><span class="sxs-lookup"><span data-stu-id="f6fe8-231">0x2000</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-232">Se impostato, il server della rubrica usa il numero normalizzato di <strong>proxyAddresses</strong>, se l'impostazione di <strong>USENORMALIZATIONRULES</strong> CMS è falsa; in caso contrario, si comporta come quando il bit del contrassegno è 0x1000.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-232">If set, Address Book Server uses the normalized number from <strong>proxyAddresses</strong>, if the <strong>UseNormalizationRules</strong> CMS setting is FALSE; otherwise it behaves the same as when the flag bit is 0x1000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6fe8-233">0x4000</span><span class="sxs-lookup"><span data-stu-id="f6fe8-233">0x4000</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-234">Se impostato, il server rubrica non include oggetti nella tabella AbUserEntry con questo valore per l'attributo specificato.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-234">If set, Address Book Server does not include objects in the AbUserEntry table that have this value for the specified attribute.</span></span> <span data-ttu-id="f6fe8-235">Se ad esempio l'attributo <strong>msRTCSIP-PrimaryUserAddress</strong> è impostato su un bit di flag, i contatti che hanno questo attributo non vengono scritti nel database.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-235">For example, if the <strong>msRTCSIP-PrimaryUserAddress</strong> attribute has this flag bit set, then contacts that have this attribute are not written to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6fe8-236">0x8000</span><span class="sxs-lookup"><span data-stu-id="f6fe8-236">0x8000</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-237">Se impostato, il server rubrica non include oggetti nella tabella AbUserEntry che non hanno questo valore per l'attributo specificato.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-237">If set, Address Book Server does not include objects in the AbUserEntry table that do not have this value for the specified attribute.</span></span> <span data-ttu-id="f6fe8-238">Se entrambi i bit del flag 0x4000 e 0x8000 sono impostati su un oggetto, l'attributo con il valore del bit di flag impostato su 0x4000 ha la precedenza e l'oggetto viene escluso dalla tabella AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-238">If both the 0x4000 and 0x8000 flag bits are set on an object, the attribute with the flag bit value set to 0x4000 takes precedence, and the object is excluded from the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6fe8-239">0x10000</span><span class="sxs-lookup"><span data-stu-id="f6fe8-239">0x10000</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-240">Se impostato, rappresenta un oggetto Group.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-240">If set, this represents a group object.</span></span> <span data-ttu-id="f6fe8-241">User Replicator usa questo bit di flag per includere i contatti con l'attributo <strong>GroupType</strong> la cui presenza indica un gruppo, ad esempio una lista di distribuzione o un gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-241">User Replicator uses this flag bit to include contacts with the <strong>groupType</strong> attribute whose presence indicates a group (for example, a distribution list or security group).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6fe8-242">0x20000</span><span class="sxs-lookup"><span data-stu-id="f6fe8-242">0x20000</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-243">Se impostato, User Replicator usa questo bit di flag per includere questo attributo nei file del server della rubrica specifica del dispositivo, ovvero i file con estensione. DAB.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-243">If set, User Replicator uses this flag bit to include this attribute in device-specific Address Book Server files (that is, files with a .dabs extension).</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f6fe8-244">Nelle versioni precedenti di Lync Server, quando si applica una modifica a Active Directory, è necessario che l'amministratore esegua **Update-CSUserDatabase** e **Update-CSAddressBook** i cmdlet di Windows PowerShell per mantenere immediatamente la modifica al database utente di Lync Server e al database di RTCab.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-244">In previous versions of Lync Server, when applying a change to Active Directory, the administrator would be required to run **Update -CSUserDatabase** and **Update –CSAddressBook** Windows PowerShell cmdlets to persist the change to the Lync Server user database and RTCab database immediately.</span></span> <span data-ttu-id="f6fe8-245">In Lync Server 2013 Lync Server User Replicator rileverà le modifiche da Active Directory e aggiornerà il database degli utenti di Lync Server in base a un intervallo configurato.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-245">In Lync Server 2013, Lync Server User Replicator will pick up the changes from Active Directory and update the Lync Server user database based on a configured interval.</span></span> <span data-ttu-id="f6fe8-246">Lync Server User Replicator propagherà rapidamente le modifiche al database di RTCab senza che l'amministratore debba eseguire Update-CSAddressBook.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-246">Lync Server User Replicator will also propagate the changes to the RTCab database quickly without the administrator having to run Update-CSAddressBook.</span></span> <span data-ttu-id="f6fe8-247">Se la query Web della Rubrica è abilitata, le modifiche verranno applicate ai risultati della ricerca da parte dei client Lync.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-247">If Address Book Web query is enabled, then the changes will be reflected in search results by Lync clients.</span></span> <span data-ttu-id="f6fe8-248">Gli amministratori dovranno eseguire solo Update-CSAddressBook se è abilitato il download di file della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-248">Administrators will only need to run Update -CSAddressBook if the Address Book file download is enabled.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f6fe8-249">Per impostazione predefinita, Lync Server User Replicator viene eseguito automaticamente ogni 5 minuti.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-249">By default Lync Server User Replicator runs automatically every 5 minutes.</span></span> <span data-ttu-id="f6fe8-250">Puoi configurare questo intervallo usando set-CSUserReplicatorConfiguration-ReplicationCycleInterval &lt; &gt;.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-250">You can configure this interval by using Set -CSUserReplicatorConfiguration -ReplicationCycleInterval &lt;&gt;.</span></span>



</div>

</div>

<div>

## <a name="filtering-the-address-book"></a><span data-ttu-id="f6fe8-251">Filtrare la Rubrica</span><span class="sxs-lookup"><span data-stu-id="f6fe8-251">Filtering the Address Book</span></span>

<span data-ttu-id="f6fe8-252">Gli utenti che popolano i file del server della rubrica possono essere controllati in base a determinati attributi di servizi di dominio Active Directory elencati nella tabella AbAttribute.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-252">The users populated in the Address Book Server files can be controlled based on certain Active Directory Domain Services attributes listed in the AbAttribute table.</span></span> <span data-ttu-id="f6fe8-253">Un attributo di questo tipo usato per filtrare è l'attributo **msExchangeHideFromAddressBook** .</span><span class="sxs-lookup"><span data-stu-id="f6fe8-253">One such attribute used for filtering is the **msExchangeHideFromAddressBook** attribute.</span></span> <span data-ttu-id="f6fe8-254">Questo è un attributo utente aggiunto dallo schema di Exchange.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-254">This is a user attribute added by the Exchange schema.</span></span> <span data-ttu-id="f6fe8-255">Se il valore di questo attributo è TRUE, Exchange Server usa questo attributo per nascondere il contatto dall'elenco indirizzi globale di Outlook.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-255">If the value of this attribute is TRUE, Exchange Server uses this attribute to hide the contact from the Outlook Global Address List (GAL).</span></span> <span data-ttu-id="f6fe8-256">Allo stesso modo, se il valore di questo attributo è TRUE, User Replicator non include l'utente nella tabella AbUserEntry e l'utente non sarà presente nei file del server della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-256">Similarly, if the value of this attribute is TRUE, User Replicator does not include that user in the AbUserEntry table and this user will not be in the Address Book Server files.</span></span>

<span data-ttu-id="f6fe8-257">Puoi usare alcuni bit di flag per definire un filtro da usare negli attributi del server della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-257">You can use some flag bits to define a filter to use on Address Book Server attributes.</span></span> <span data-ttu-id="f6fe8-258">Ad esempio, la presenza di alcuni bit di flag può identificare un attributo come attributo include o come attributo Exclude.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-258">For example, the presence of certain flag bits can identify an attribute as an include attribute or an exclude attribute.</span></span> <span data-ttu-id="f6fe8-259">User Replicator filtra i contatti che contengono un attributo Exclude e filtra i Contains che non contengono un attributo include.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-259">User Replicator filters out contacts that contain an exclude attribute and filters out contains that do not contain an include attribute.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="f6fe8-260">Per altre informazioni su come filtrare la Rubrica, vedere <A href="https://technet.microsoft.com/en-us/library/gg415643(v=ocs.15)">cmdlet del server rubrica in Lync server 2013</A>e filtrare la <A href="http://go.microsoft.com/fwlink/?linkid=330430">rubrica di Lync 2013</A></span><span class="sxs-lookup"><span data-stu-id="f6fe8-260">For more information about filtering the Address Book, see <A href="https://technet.microsoft.com/en-us/library/gg415643(v=ocs.15)">Address Book Server cmdlets in Lync Server 2013</A>, and <A href="http://go.microsoft.com/fwlink/?linkid=330430">Filter Lync 2013 address book</A></span></span>



</div>

<span data-ttu-id="f6fe8-261">Attualmente esistono tre filtri diversi.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-261">Currently, there are three different filters.</span></span> <span data-ttu-id="f6fe8-262">Nella tabella seguente sono elencati questi filtri.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-262">The following table lists these filters.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f6fe8-263">Attributo</span><span class="sxs-lookup"><span data-stu-id="f6fe8-263">Attribute</span></span></th>
<th><span data-ttu-id="f6fe8-264">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f6fe8-264">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f6fe8-265">0x800</span><span class="sxs-lookup"><span data-stu-id="f6fe8-265">0x800</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-266">Se impostato, identifica un attributo obbligatorio per un contatto.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-266">If set, this identifies a required attribute for a contact.</span></span> <span data-ttu-id="f6fe8-267">User Replicator usa questo bit di flag per filtrare i contatti che non contengono almeno un attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-267">User Replicator uses this flag bit to filter out contacts that do not contain at least one required attribute.</span></span> <span data-ttu-id="f6fe8-268">OuPathId è un attributo obbligatorio, che è sempre impostato.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-268">The OuPathId is a required attribute, which is always set.</span></span> <span data-ttu-id="f6fe8-269">Quindi deve essere impostato almeno uno degli altri attributi obbligatori.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-269">So at least one of other required attributes should be set.</span></span> <span data-ttu-id="f6fe8-270">In caso contrario, il contatto (ovvero, con il valore dell'attributo obbligatorio OuPathId) non verrà ancora scritto nel database.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-270">Otherwise, contact (that is, with value of required attribute OuPathId) will still not be written to database.</span></span> <span data-ttu-id="f6fe8-271">Se ad esempio <strong>telephoneNumber</strong> e <strong>HomePhone</strong> sono definiti come attributi obbligatori, nel database verranno scritti solo i contatti che hanno almeno uno di questi attributi.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-271">For example, if <strong>telephoneNumber</strong> and <strong>homePhone</strong> are defined as required attributes, only the contacts that have at least one of these attributes are written to the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6fe8-272">0x4000</span><span class="sxs-lookup"><span data-stu-id="f6fe8-272">0x4000</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-273">Se impostato, identifica un attributo Exclude.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-273">If set, this identifies an exclude attribute.</span></span> <span data-ttu-id="f6fe8-274">User Replicator usa questo bit di flag per filtrare i contatti che contengono questo attributo.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-274">User Replicator uses this flag bit to filter out contacts that contain this attribute.</span></span> <span data-ttu-id="f6fe8-275">Ad esempio, se <strong>msRTCSIP-PrimaryUserAddress</strong> è definito come attributo Exclude, i contatti che hanno questo attributo non vengono scritti nel database.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-275">For example, if <strong>msRTCSIP-PrimaryUserAddress</strong> is defined as an exclude attribute, contacts that have this attribute are not written to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6fe8-276">0x8000</span><span class="sxs-lookup"><span data-stu-id="f6fe8-276">0x8000</span></span></p></td>
<td><p><span data-ttu-id="f6fe8-277">Se impostato, identifica un attributo include.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-277">If set, this identifies an include attribute.</span></span> <span data-ttu-id="f6fe8-278">User Replicator usa questo bit di flag per filtrare i contatti che non contengono questo attributo.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-278">User Replicator uses this flag bit to filter out contacts that do not contain this attribute.</span></span> <span data-ttu-id="f6fe8-279">Ad esempio, se <strong>msRTCSIP-PrimaryUserAddress</strong> è definito come attributo include, nel database verranno scritti solo i contatti con questo attributo.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-279">For example, if <strong>msRTCSIP-PrimaryUserAddress</strong> is defined as an include attribute, only the contacts that have this attribute are written to the database.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="f6fe8-280">Se sono impostati entrambi i bit di flag 0x4000 (Exclude Attribute) e 0x8000 (include Attribute), il bit 0x4000 esegue l'override del bit 0x8000 e il contatto viene escluso.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-280">If both the 0x4000 (exclude attribute) and 0x8000 (include attribute) flag bits are set, the 0x4000 bit overrides the 0x8000 bit and the contact is excluded.</span></span>



</div>

<span data-ttu-id="f6fe8-281">Anche se è possibile filtrare la Rubrica per includere solo determinati utenti, la limitazione delle voci non limita la possibilità di altri utenti di contattare gli utenti filtrati o di vederne lo stato presenza.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-281">Although you can filter the Address Book to include only certain users, limiting entries does not limit other users' ability to contact the filtered users or to see their presence status.</span></span> <span data-ttu-id="f6fe8-282">Gli utenti possono sempre trovare, inviare manualmente messaggi istantanei o avviare manualmente le chiamate agli utenti non presenti nella rubrica immettendo il nome di accesso completo di un utente.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-282">Users can always find, manually send instant messages, or manually initiate calls to users not in the Address Book by entering a user's complete sign-in name.</span></span> <span data-ttu-id="f6fe8-283">Inoltre, le informazioni di contatto per un utente possono essere trovate anche in Outlook.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-283">Also, contact information for a user could also be found in Outlook.</span></span>

<span data-ttu-id="f6fe8-284">Pur avendo i record di contatto completo nei file della Rubrica, è possibile usare Lync Server per avviare la posta elettronica, il telefono o le chiamate vocali aziendali (ovvero, se Enterprise Voice è abilitato sul server) con utenti non configurati per l'avvio della sessione Protocol (SIP), alcune organizzazioni preferiscono includere solo gli utenti abilitati per SIP nelle voci del server rubrica.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-284">While having full contact records in the Address Book files enables you to use Lync Server to initiate email, telephone, or Enterprise Voice calls (that is, if Enterprise Voice is enabled on the server) with users that are not configured for Session Initiation Protocol (SIP), some organizations prefer to include only SIP-enabled users in their Address Book Server entries.</span></span> <span data-ttu-id="f6fe8-285">È possibile filtrare la Rubrica per includere solo gli utenti abilitati per SIP deselezionando il bit 0x800 nella colonna **Flags** degli attributi obbligatori seguenti: **mailNickname**, **telephoneNumber**, **HomePhone**e **mobile**.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-285">You can filter the Address Book to include only SIP-enabled users by clearing the 0x800 bit in the **Flags** column of the following required attributes: **mailNickname**, **telephoneNumber**, **homePhone**, and **mobile**.</span></span> <span data-ttu-id="f6fe8-286">È anche possibile filtrare la Rubrica per includere solo gli utenti abilitati per SIP impostando 0x8000 (attributo include) nella colonna **Flags** dell'attributo **msRTCSIP-PrimaryUserAddress** .</span><span class="sxs-lookup"><span data-stu-id="f6fe8-286">You can also filter the Address Book to include only SIP-enabled users by setting the 0x8000 (include attribute) in the **Flags** column of the **msRTCSIP-PrimaryUserAddress** attribute.</span></span> <span data-ttu-id="f6fe8-287">Questo consente inoltre di escludere gli account di servizio dai file della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-287">This also helps to exclude service accounts from the Address Book files.</span></span>

<span data-ttu-id="f6fe8-288">Dopo aver modificato la tabella AbAttribute, è possibile aggiornare i dati nella tabella AbUserEntry eseguendo il comando **Update-CsUserDatabase** cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-288">After you modify the AbAttribute table, you can refresh the data in the AbUserEntry table by running the cmdlet **Update-CsUserDatabase** command.</span></span> <span data-ttu-id="f6fe8-289">Dopo il completamento della replica UR, è possibile aggiornare il file nell'archivio file della rubrica eseguendo manualmente il comando **UpdateCsAddressBook** cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-289">After UR replication completes, you can update the file in the Address Book Server file store by manually running the cmdlet **UpdateCsAddressBook** command.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f6fe8-290">Il server front-end in cui è posizionato il server della Rubrica non è configurabile in termini amministrativi.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-290">The Front End Server that the Address Book Server is placed is not administratively configurable.</span></span> <span data-ttu-id="f6fe8-291">Una viene scelta durante la distribuzione, in genere il primo server front-end distribuito.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-291">One is chosen during deployment—typically, the first Front End Server deployed.</span></span> <span data-ttu-id="f6fe8-292">In caso di errore, il servizio Rubrica verrà spostato in un altro server front-end e non richiede alcuna attenzione amministrativa.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-292">In the event of failure, the Address Book Service will move to another Front End Server, and requires no administrative attention.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f6fe8-293">Se l'infrastruttura è stata consolidata o modificata in altro modo da una distribuzione a più foreste o da una distribuzione padre/figlio, ad esempio il consolidamento dell'infrastruttura prima di passare a Lync Server, è possibile che il download del servizio Rubrica e la query Web della Rubrica non siano disponibili per alcuni utenti.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-293">If you have consolidated or otherwise modified your infrastructure from a multi-forest deployment or a parent/child deployment (such as consolidating your infrastructure before moving to Lync Server), you may find that the Address Book service download and the Address Book Web Query fails for some users.</span></span> <span data-ttu-id="f6fe8-294">Quando si trova in una distribuzione con più domini o insiemi di foreste, l'attributo <STRONG>msRTCSIP-OriginatorSID</STRONG> viene popolato negli oggetti utente che presentano il problema.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-294">When in a deployment that had multiple domains or forests, the attribute <STRONG>MsRTCSIP-OriginatorSid</STRONG> is populated on the user objects that are exhibiting the issue.</span></span> <span data-ttu-id="f6fe8-295">L'attributo <STRONG>msRTCSIP-OriginatorSID</STRONG> deve essere impostato su null per questi oggetti per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="f6fe8-295">The <STRONG>MsRTCSIP-OriginatorSid</STRONG> attribute must be set to NULL on these objects to resolve the issue.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

