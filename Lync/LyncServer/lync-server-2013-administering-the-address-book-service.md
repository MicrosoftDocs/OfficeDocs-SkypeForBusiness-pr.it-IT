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
ms.openlocfilehash: 45dbc2c71cf34515f8f6176e4f579e6683ad319e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146259"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="administering-the-address-book-service-in-lync-server-2013"></a><span data-ttu-id="41c86-102">Amministrazione del servizio Rubrica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41c86-102">Administering the Address Book Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41c86-103">_**Ultimo argomento modificato:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="41c86-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="41c86-104">Come parte della distribuzione di Lync Server, Enterprise Edition o il server Standard Edition, il servizio Rubrica è installato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="41c86-104">As a part of the deployment of Lync Server, Enterprise Edition or Standard Edition server, the Address Book Service is installed by default.</span></span> <span data-ttu-id="41c86-105">Il database utilizzato dal servizio Rubrica – RTCab – viene creato in SQL Server (per Enterprise Edition, questo è il server SQL back-end, per il server Standard Edition, il server SQL collocato).</span><span class="sxs-lookup"><span data-stu-id="41c86-105">The database used by the Address Book Service – RTCab – is created on the SQL Server (for Enterprise Edition, this is the back-end SQL Server; for Standard Edition server, the collocated SQL Server).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="41c86-106">Per informazioni sull'utilizzo di <STRONG>ADSI Edit</STRONG> per modificare gli attributi degli oggetti di servizi di dominio Active Directory, vedere <A href="https://go.microsoft.com/fwlink/?linkid=330427">ADSI Edit</A>.</span><span class="sxs-lookup"><span data-stu-id="41c86-106">For information about using <STRONG>ADSI Edit</STRONG> to edit Active Directory Domain Services object attributes, see <A href="https://go.microsoft.com/fwlink/?linkid=330427">ADSI Edit</A>.</span></span> <span data-ttu-id="41c86-107">Per informazioni su uno strumento nel Resource Kit specifico per il servizio Rubrica, vedere <A href="https://go.microsoft.com/fwlink/?linkid=330429">Microsoft Lync Server 2013 Resource Kit Tools</A>.</span><span class="sxs-lookup"><span data-stu-id="41c86-107">For information about a tool in the Resource Kit specifically for the Address Book service, see <A href="https://go.microsoft.com/fwlink/?linkid=330429">Microsoft Lync Server 2013 Resource Kit Tools</A>.</span></span>



</div>

<div>

## <a name="address-book-server-phone-number-normalization"></a><span data-ttu-id="41c86-108">Normalizzazione dei numeri di telefono del server della Rubrica</span><span class="sxs-lookup"><span data-stu-id="41c86-108">Address Book Server Phone Number Normalization</span></span>

<span data-ttu-id="41c86-109">Lync Server richiede numeri di telefono RFC 3966/E. 164 standardizzati.</span><span class="sxs-lookup"><span data-stu-id="41c86-109">Lync Server requires standardized RFC 3966/E.164 phone numbers.</span></span> <span data-ttu-id="41c86-110">Per utilizzare numeri di telefono non strutturati o formattati in modo incoerente, Lync Server si basa sul server della Rubrica per preelaborare i numeri di telefono prima di essere trasportati alle regole di normalizzazione.</span><span class="sxs-lookup"><span data-stu-id="41c86-110">To use phone numbers that are unstructured or inconsistently formatted, Lync Server relies on the Address Book Server to preprocess phone numbers before they are handed off to the normalization rules.</span></span> <span data-ttu-id="41c86-111">Quando viene utilizzato un numero di telefono dalla Rubrica e viene applicata la regola di normalizzazione, i client, ad esempio Lync Phone Edition e Lync mobile, possono utilizzare questi numeri normalizzati.</span><span class="sxs-lookup"><span data-stu-id="41c86-111">When a phone number is used from the address book and the normalization rule is applied, clients, such as Lync Phone Edition and Lync Mobile, can use these normalized numbers.</span></span>

<span data-ttu-id="41c86-p104">Le regole di normalizzazione utilizzate nelle versioni precedenti potrebbero non funzionare correttamente senza alcune modifiche. Poiché gli spazi vuoti e i caratteri non obbligatori vengono rimossi prima delle regole di normalizzazione, se l'espressione regex cerca in modo specifico un trattino o un altro carattere che è stato rimosso, la regola di normalizzazione potrebbe non riuscire. È opportuno esaminare le regole di normalizzazione per garantire che non cerchino questi caratteri non obbligatori o che un errore della regola non impedisca la continuazione nel caso in cui il carattere non sia presente dove previsto dalla regola stessa.</span><span class="sxs-lookup"><span data-stu-id="41c86-p104">The normalization rules that were used in previous versions may not work properly without some adjustments. Because the white space and non-mandatory characters are removed prior to the normalization rules, if your regex expression is specifically looking for a dash or other character that was removed, your normalization rule might fail. You should review your normalization rules to ensure that either they are not looking for these non-mandatory characters, or that the rule can fail gracefully and continue in the event that the character is not present where the rule anticipates it will be.</span></span>

</div>

<div>

## <a name="user-replicator-and-address-book-server"></a><span data-ttu-id="41c86-115">User Replicator e server della Rubrica</span><span class="sxs-lookup"><span data-stu-id="41c86-115">User Replicator and Address Book Server</span></span>

<span data-ttu-id="41c86-116">Il server della Rubrica utilizza i dati forniti da User Replicator per aggiornare le informazioni ottenute inizialmente dall'elenco indirizzi globale.</span><span class="sxs-lookup"><span data-stu-id="41c86-116">The Address Book Server uses data provided by User Replicator to update the information that it initially obtains from the global address list (GAL).</span></span> <span data-ttu-id="41c86-117">User Replicator scrive gli attributi dei servizi di dominio Active Directory per ogni utente, contatto e gruppo nella tabella AbUserEntry del database e il server della rubrica sincronizza i dati degli utenti dal database in file nell'archivio file del server della Rubrica e nel database della rubrica RTCab.</span><span class="sxs-lookup"><span data-stu-id="41c86-117">User Replicator writes the Active Directory Domain Services attributes for each user, contact, and group into the AbUserEntry table in the database and the Address Book Server syncs the user data from the database into files in the Address Book Server file store and into the Address Book database RTCab.</span></span> <span data-ttu-id="41c86-118">Lo schema per la tabella AbUserEntry prevede l'utilizzo di due colonne, **UserGuid** e **UserData**.</span><span class="sxs-lookup"><span data-stu-id="41c86-118">The schema for the AbUserEntry table uses two columns, **UserGuid** and **UserData**.</span></span> <span data-ttu-id="41c86-119">**UserGuid** è la colonna di indice e contiene il GUID a 16 byte dell'oggetto Active Directory.</span><span class="sxs-lookup"><span data-stu-id="41c86-119">**UserGuid** is the index column and contains the 16-byte GUID of the Active Directory object.</span></span> <span data-ttu-id="41c86-120">**UserData** è una colonna di tipo immagine che contiene tutti gli attributi di servizi di dominio Active Directory descritti in precedenza per il contatto.</span><span class="sxs-lookup"><span data-stu-id="41c86-120">**UserData** is an image column which contains all of the previously mentioned Active Directory Domain Services attributes for that contact.</span></span>

<span data-ttu-id="41c86-121">User Replicator determina quali attributi di Active Directory scrivere leggendo una tabella di configurazione che si trova nella stessa istanza basata su SQL Server della tabella AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="41c86-121">User Replicator determines which Active Directory attributes to write by reading a configuration table located in the same SQL Server-based instance as the AbUserEntry table.</span></span> <span data-ttu-id="41c86-122">La tabella AbAttribute contiene tre colonne, **ID**, **Name**, **Flags** e **Enable**.</span><span class="sxs-lookup"><span data-stu-id="41c86-122">The AbAttribute table contains three columns, **ID**, **Name**, **Flags**, and **Enable**.</span></span> <span data-ttu-id="41c86-123">La tabella viene creata durante l'impostazione del database.</span><span class="sxs-lookup"><span data-stu-id="41c86-123">The table is created during database setup.</span></span> <span data-ttu-id="41c86-124">Se la tabella AbAttribute è vuota,User Replicator ignora la logica di elaborazione della tabella AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="41c86-124">If the AbAttribute table is empty, User Replicator skips its AbUserEntry table processing logic.</span></span> <span data-ttu-id="41c86-125">Gli attributi del server della Rubrica sono dinamici e vengono recuperati dalla tabella AbAttribute, che viene inizialmente scritta dal server della Rubrica quando questo viene attivato.</span><span class="sxs-lookup"><span data-stu-id="41c86-125">Address Book Server attributes are dynamic and are retrieved from the AbAttribute table, which is initially written by the Address Book Server when the Address Book Server is activated.</span></span>

<span data-ttu-id="41c86-126">L'attivazione del server rubrica inserisce nella tabella AbAttribute i valori riportati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="41c86-126">Address Book Server activation populates the AbAttribute table with the values shown in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="41c86-127">ID</span><span class="sxs-lookup"><span data-stu-id="41c86-127">ID</span></span></th>
<th><span data-ttu-id="41c86-128">Name</span><span class="sxs-lookup"><span data-stu-id="41c86-128">Name</span></span></th>
<th><span data-ttu-id="41c86-129">Bandiere</span><span class="sxs-lookup"><span data-stu-id="41c86-129">Flags</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41c86-130">1</span><span class="sxs-lookup"><span data-stu-id="41c86-130">1</span></span></p></td>
<td><p><span data-ttu-id="41c86-131">givenName</span><span class="sxs-lookup"><span data-stu-id="41c86-131">givenName</span></span></p></td>
<td><p><span data-ttu-id="41c86-132">0x01400000</span><span class="sxs-lookup"><span data-stu-id="41c86-132">0x01400000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c86-133">2</span><span class="sxs-lookup"><span data-stu-id="41c86-133">2</span></span></p></td>
<td><p><span data-ttu-id="41c86-134">Sn</span><span class="sxs-lookup"><span data-stu-id="41c86-134">Sn</span></span></p></td>
<td><p><span data-ttu-id="41c86-135">0x02400000</span><span class="sxs-lookup"><span data-stu-id="41c86-135">0x02400000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c86-136">3</span><span class="sxs-lookup"><span data-stu-id="41c86-136">3</span></span></p></td>
<td><p><span data-ttu-id="41c86-137">displayName</span><span class="sxs-lookup"><span data-stu-id="41c86-137">displayName</span></span></p></td>
<td><p><span data-ttu-id="41c86-138">0x03420000</span><span class="sxs-lookup"><span data-stu-id="41c86-138">0x03420000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c86-139">4</span><span class="sxs-lookup"><span data-stu-id="41c86-139">4</span></span></p></td>
<td><p><span data-ttu-id="41c86-140">Titolo</span><span class="sxs-lookup"><span data-stu-id="41c86-140">Title</span></span></p></td>
<td><p><span data-ttu-id="41c86-141">0x04000000</span><span class="sxs-lookup"><span data-stu-id="41c86-141">0x04000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c86-142">5</span><span class="sxs-lookup"><span data-stu-id="41c86-142">5</span></span></p></td>
<td><p><span data-ttu-id="41c86-143">mailNickname</span><span class="sxs-lookup"><span data-stu-id="41c86-143">mailNickname</span></span></p></td>
<td><p><span data-ttu-id="41c86-144">0x05400000</span><span class="sxs-lookup"><span data-stu-id="41c86-144">0x05400000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c86-145">6 </span><span class="sxs-lookup"><span data-stu-id="41c86-145">6</span></span></p></td>
<td><p><span data-ttu-id="41c86-146">Company</span><span class="sxs-lookup"><span data-stu-id="41c86-146">Company</span></span></p></td>
<td><p><span data-ttu-id="41c86-147">0x06000000</span><span class="sxs-lookup"><span data-stu-id="41c86-147">0x06000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c86-148">7 </span><span class="sxs-lookup"><span data-stu-id="41c86-148">7</span></span></p></td>
<td><p><span data-ttu-id="41c86-149">physicalDeliveryOfficeName</span><span class="sxs-lookup"><span data-stu-id="41c86-149">physicalDeliveryOfficeName</span></span></p></td>
<td><p><span data-ttu-id="41c86-150">0x07000000</span><span class="sxs-lookup"><span data-stu-id="41c86-150">0x07000000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c86-151">8 </span><span class="sxs-lookup"><span data-stu-id="41c86-151">8</span></span></p></td>
<td><p><span data-ttu-id="41c86-152">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="41c86-152">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="41c86-153">0x08520C00</span><span class="sxs-lookup"><span data-stu-id="41c86-153">0x08520C00</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c86-154">9 </span><span class="sxs-lookup"><span data-stu-id="41c86-154">9</span></span></p></td>
<td><p><span data-ttu-id="41c86-155">telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="41c86-155">telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="41c86-156">0x09022800</span><span class="sxs-lookup"><span data-stu-id="41c86-156">0x09022800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c86-157">10 </span><span class="sxs-lookup"><span data-stu-id="41c86-157">10</span></span></p></td>
<td><p><span data-ttu-id="41c86-158">homePhone</span><span class="sxs-lookup"><span data-stu-id="41c86-158">homePhone</span></span></p></td>
<td><p><span data-ttu-id="41c86-159">0x0A302800</span><span class="sxs-lookup"><span data-stu-id="41c86-159">0x0A302800</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c86-160">11 </span><span class="sxs-lookup"><span data-stu-id="41c86-160">11</span></span></p></td>
<td><p><span data-ttu-id="41c86-161">Cellulare</span><span class="sxs-lookup"><span data-stu-id="41c86-161">Mobile</span></span></p></td>
<td><p><span data-ttu-id="41c86-162">0x0B622800</span><span class="sxs-lookup"><span data-stu-id="41c86-162">0x0B622800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c86-163">12</span><span class="sxs-lookup"><span data-stu-id="41c86-163">12</span></span></p></td>
<td><p><span data-ttu-id="41c86-164">otherTelephone</span><span class="sxs-lookup"><span data-stu-id="41c86-164">otherTelephone</span></span></p></td>
<td><p><span data-ttu-id="41c86-165">0x0C302000</span><span class="sxs-lookup"><span data-stu-id="41c86-165">0x0C302000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c86-166">13</span><span class="sxs-lookup"><span data-stu-id="41c86-166">13</span></span></p></td>
<td><p><span data-ttu-id="41c86-167">ipPhone</span><span class="sxs-lookup"><span data-stu-id="41c86-167">ipPhone</span></span></p></td>
<td><p><span data-ttu-id="41c86-168">0x0D302000</span><span class="sxs-lookup"><span data-stu-id="41c86-168">0x0D302000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c86-169">14 </span><span class="sxs-lookup"><span data-stu-id="41c86-169">14</span></span></p></td>
<td><p><span data-ttu-id="41c86-170">Posta</span><span class="sxs-lookup"><span data-stu-id="41c86-170">Mail</span></span></p></td>
<td><p><span data-ttu-id="41c86-171">0x0E500000</span><span class="sxs-lookup"><span data-stu-id="41c86-171">0x0E500000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c86-172">15 </span><span class="sxs-lookup"><span data-stu-id="41c86-172">15</span></span></p></td>
<td><p><span data-ttu-id="41c86-173">groupType</span><span class="sxs-lookup"><span data-stu-id="41c86-173">groupType</span></span></p></td>
<td><p><span data-ttu-id="41c86-174">0x0F010800</span><span class="sxs-lookup"><span data-stu-id="41c86-174">0x0F010800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c86-175">16 </span><span class="sxs-lookup"><span data-stu-id="41c86-175">16</span></span></p></td>
<td><p><span data-ttu-id="41c86-176">Reparto</span><span class="sxs-lookup"><span data-stu-id="41c86-176">Department</span></span></p></td>
<td><p><span data-ttu-id="41c86-177">0x10000000</span><span class="sxs-lookup"><span data-stu-id="41c86-177">0x10000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c86-178">17 </span><span class="sxs-lookup"><span data-stu-id="41c86-178">17</span></span></p></td>
<td><p><span data-ttu-id="41c86-179">Descrizione</span><span class="sxs-lookup"><span data-stu-id="41c86-179">Description</span></span></p></td>
<td><p><span data-ttu-id="41c86-180">0x11000100</span><span class="sxs-lookup"><span data-stu-id="41c86-180">0x11000100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c86-181">18 </span><span class="sxs-lookup"><span data-stu-id="41c86-181">18</span></span></p></td>
<td><p><span data-ttu-id="41c86-182">Manager</span><span class="sxs-lookup"><span data-stu-id="41c86-182">Manager</span></span></p></td>
<td><p><span data-ttu-id="41c86-183">0x12040001</span><span class="sxs-lookup"><span data-stu-id="41c86-183">0x12040001</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c86-184">19</span><span class="sxs-lookup"><span data-stu-id="41c86-184">19</span></span></p></td>
<td><p><span data-ttu-id="41c86-185">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="41c86-185">proxyAddress</span></span></p></td>
<td><p><span data-ttu-id="41c86-186">0x00500105</span><span class="sxs-lookup"><span data-stu-id="41c86-186">0x00500105</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c86-187">20</span><span class="sxs-lookup"><span data-stu-id="41c86-187">20</span></span></p></td>
<td><p><span data-ttu-id="41c86-188">msExchHideFromAddressLists</span><span class="sxs-lookup"><span data-stu-id="41c86-188">msExchHideFromAddressLists</span></span></p></td>
<td><p><span data-ttu-id="41c86-189">0xFF000003</span><span class="sxs-lookup"><span data-stu-id="41c86-189">0xFF000003</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c86-190">99</span><span class="sxs-lookup"><span data-stu-id="41c86-190">99</span></span></p></td>
<td><p><span data-ttu-id="41c86-191">entryID</span><span class="sxs-lookup"><span data-stu-id="41c86-191">entryID</span></span></p></td>
<td><p><span data-ttu-id="41c86-192">0x99000000</span><span class="sxs-lookup"><span data-stu-id="41c86-192">0x99000000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="41c86-193">I numeri nella colonna **ID** devono essere univoci e non devono mai essere riutilizzati.</span><span class="sxs-lookup"><span data-stu-id="41c86-193">The numbers in the **ID** column must be unique and should never be reused.</span></span> <span data-ttu-id="41c86-194">Inoltre, mantenendo i valori ID inferiori a 256, si risparmia spazio nei file di output scritti dal server della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="41c86-194">Also, keeping the ID values under 256 saves space in the output files written by the Address Book Server.</span></span> <span data-ttu-id="41c86-195">Tuttavia, il valore ID massimo è 65535.</span><span class="sxs-lookup"><span data-stu-id="41c86-195">However, the maximum ID value is 65535.</span></span> <span data-ttu-id="41c86-196">La colonna **Name** corrisponde al nome di attributo di Active Directory che User Replicator deve inserire nella tabella AbUserEntry per ogni contatto.</span><span class="sxs-lookup"><span data-stu-id="41c86-196">The **Name** column corresponds to the Active Directory attribute name that User Replicator should put in the AbUserEntry table for each contact.</span></span> <span data-ttu-id="41c86-197">Il valore nella colonna **Flags** è utilizzato per definire il tipo di attributo.</span><span class="sxs-lookup"><span data-stu-id="41c86-197">The value in the **Flags** column is used to define the type of attribute.</span></span> <span data-ttu-id="41c86-198">I tipi seguenti di attributi del server della Rubrica sono riconosciuti da User Replicator, indicati dal bit basso del valore nella colonna **Flags**.</span><span class="sxs-lookup"><span data-stu-id="41c86-198">The following types of Address Book Server attributes are recognized by User Replicator, indicated by the low byte of the value in the **Flags** column.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="41c86-199">Attributo</span><span class="sxs-lookup"><span data-stu-id="41c86-199">Attribute</span></span></th>
<th><span data-ttu-id="41c86-200">Descrizione</span><span class="sxs-lookup"><span data-stu-id="41c86-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41c86-201">0x0</span><span class="sxs-lookup"><span data-stu-id="41c86-201">0x0</span></span></p></td>
<td><p><span data-ttu-id="41c86-p108">Attributo stringa. Questo tipo viene convertito da User Replicator in formato UTF-8 prima dell'archiviazione nella tabella AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="41c86-p108">A string attribute. User Replicator converts this type to UTF-8 before storing it in the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c86-204">0x1</span><span class="sxs-lookup"><span data-stu-id="41c86-204">0x1</span></span></p></td>
<td><p><span data-ttu-id="41c86-p109">Attributo binario. Viene archiviato da User Replicator nell'oggetto blob senza alcuna conversione.</span><span class="sxs-lookup"><span data-stu-id="41c86-p109">A binary attribute. User Replicator stores this in the blob without any conversion.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c86-207">0x2</span><span class="sxs-lookup"><span data-stu-id="41c86-207">0x2</span></span></p></td>
<td><p><span data-ttu-id="41c86-208">Un attributo stringa, ma è incluso solo se il valore dell'attributo inizia &quot;con Tel&quot;:.</span><span class="sxs-lookup"><span data-stu-id="41c86-208">A string attribute, but is included only if the attribute value begins with &quot;tel:&quot;.</span></span> <span data-ttu-id="41c86-209">È utilizzato principalmente per attributi stringa multivalore, in particolare <strong>proxyAddresses</strong>.</span><span class="sxs-lookup"><span data-stu-id="41c86-209">This is primarily for multi-valued string attributes, specifically <strong>proxyAddresses</strong>.</span></span> <span data-ttu-id="41c86-210">In questo caso, il server della Rubrica è interessato solo alle voci di <strong>proxyAddresses</strong> che &quot;iniziano con&quot;Tel:.</span><span class="sxs-lookup"><span data-stu-id="41c86-210">In this case, Address Book Server is interested only in <strong>proxyAddresses</strong> entries that begin with &quot;tel:&quot;.</span></span> <span data-ttu-id="41c86-211">Pertanto, nell'interesse di risparmiare spazio, User Replicator archivia solo le voci che iniziano con &quot;Tel:.&quot;</span><span class="sxs-lookup"><span data-stu-id="41c86-211">Therefore, in the interest of saving space, User Replicator stores only the entries that begin with &quot;tel:&quot;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c86-212">0x3</span><span class="sxs-lookup"><span data-stu-id="41c86-212">0x3</span></span></p></td>
<td><p><span data-ttu-id="41c86-p111">Attributo stringa booleano. Se l'impostazione è TRUE, il contatto non viene incluso da User Replicator nella tabella AbUserEntry. Se l'impostazione è FALSE, gli attributi per il contatto vengono inclusi da User Replicator nella tabella AbUserEntry, ad eccezione dell'attributo specifico con questo flag. Si tratta di un altro tipo di caso speciale utilizzato principalmente per l'attributo <strong>msExchHideFromAddressLists</strong>.</span><span class="sxs-lookup"><span data-stu-id="41c86-p111">A Boolean string attribute, which if TRUE causes User Replicator to not include this contact in the AbUserEntry table. If FALSE, it causes User Replicator to include the attributes for this contact in the AbUserEntry table, but not the particular attribute with this flag. This is another special case type that is primarily for the <strong>msExchHideFromAddressLists</strong> attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c86-216">0x4</span><span class="sxs-lookup"><span data-stu-id="41c86-216">0x4</span></span></p></td>
<td><p><span data-ttu-id="41c86-217">Un attributo stringa, ma è incluso solo se il valore dell'attributo inizia &quot;con SMTP&quot; : e include &quot; @ &quot; il simbolo.</span><span class="sxs-lookup"><span data-stu-id="41c86-217">A string attribute, but is included only if the attribute value begins with &quot;smtp:&quot; and includes the &quot;@&quot; symbol.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c86-218">0x5</span><span class="sxs-lookup"><span data-stu-id="41c86-218">0x5</span></span></p></td>
<td><p><span data-ttu-id="41c86-219">Un attributo stringa, ma è incluso solo se il valore dell'attributo inizia con &quot;Tel:&quot; o &quot;SMTP:&quot; e include il &quot; @ &quot; simbolo.</span><span class="sxs-lookup"><span data-stu-id="41c86-219">A string attribute, but is included only if the attribute value begins with either &quot;tel:&quot; or &quot;smtp:&quot; and includes the &quot;@&quot; symbol.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c86-220">0x100</span><span class="sxs-lookup"><span data-stu-id="41c86-220">0x100</span></span></p></td>
<td><p><span data-ttu-id="41c86-221">Se impostato, si tratta di un attributo multivalore che può essere presente più volte per ogni contatto.</span><span class="sxs-lookup"><span data-stu-id="41c86-221">If set, this is a multi-valued attribute that can appear more than once for each contact.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c86-222">0x400</span><span class="sxs-lookup"><span data-stu-id="41c86-222">0x400</span></span></p></td>
<td><p><span data-ttu-id="41c86-p112">Se impostato, identifica l'attributo del nome account utente di posta elettronica per un contatto. Questo flag viene utilizzato dal server della Rubrica per identificare il valore di attributo da visualizzare nella voce del registro eventi di normalizzazione del telefono.</span><span class="sxs-lookup"><span data-stu-id="41c86-p112">If set, this identifies the email user account name attribute for a contact. Address Book Server uses this flag to identify which attribute value to show in the phone normalization event log entry.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c86-225">0x800</span><span class="sxs-lookup"><span data-stu-id="41c86-225">0x800</span></span></p></td>
<td><p><span data-ttu-id="41c86-p113">Se impostato, identifica un attributo obbligatorio per un contatto. Il server della Rubrica include un utente nella tabella AbUserEntry solo se è presente un valore per questo attributo in Active Directory. Se sono presenti più attributi obbligatori, è necessario che solo uno di essi disponga di un valore per includere l'utente nella tabella AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="41c86-p113">If set, this identifies a required attribute for a contact. Address Book Server includes a user in the AbUserEntry table only if there is a value for this attribute in Active Directory. If there is more than one required attribute, only one of them is required to have a value to include the user in the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c86-229">0x1000</span><span class="sxs-lookup"><span data-stu-id="41c86-229">0x1000</span></span></p></td>
<td><p><span data-ttu-id="41c86-230">Se impostato, il valore di questo attributo viene sempre normalizzato dal server della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="41c86-230">If set, Address Book Server always normalizes the value of this attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c86-231">0x2000</span><span class="sxs-lookup"><span data-stu-id="41c86-231">0x2000</span></span></p></td>
<td><p><span data-ttu-id="41c86-232">Se impostato, il server della Rubrica utilizza il numero normalizzato di <strong>proxyAddresses</strong>, se l'impostazione CMS di <strong>UseNormalizationRules</strong> è FALSE; in caso contrario, il comportamento corrisponde a quello che si verifica quando il bit di flag è 0x1000.</span><span class="sxs-lookup"><span data-stu-id="41c86-232">If set, Address Book Server uses the normalized number from <strong>proxyAddresses</strong>, if the <strong>UseNormalizationRules</strong> CMS setting is FALSE; otherwise it behaves the same as when the flag bit is 0x1000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c86-233">0x4000</span><span class="sxs-lookup"><span data-stu-id="41c86-233">0x4000</span></span></p></td>
<td><p><span data-ttu-id="41c86-p114">Se impostato, il server della Rubrica non include nella tabella AbUserEntry oggetti con questo valore per l'attributo specificato. Se, ad esempio, per l'attributo <strong>msRTCSIP-PrimaryUserAddress</strong> è impostato questo bit di flag, i contatti con questo attributo non vengono scritti nel database.</span><span class="sxs-lookup"><span data-stu-id="41c86-p114">If set, Address Book Server does not include objects in the AbUserEntry table that have this value for the specified attribute. For example, if the <strong>msRTCSIP-PrimaryUserAddress</strong> attribute has this flag bit set, then contacts that have this attribute are not written to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c86-236">0x8000</span><span class="sxs-lookup"><span data-stu-id="41c86-236">0x8000</span></span></p></td>
<td><p><span data-ttu-id="41c86-p115">Se impostato, il server della Rubrica non include nella tabella AbUserEntry oggetti che non hanno questo valore per l'attributo specificato. Se entrambi i bit di flag 0x4000 e 0x8000 sono impostati in un oggetto, l'attributo con il valore del bit di flag impostato su 0x4000 ha la precedenza e l'oggetto viene escluso dalla tabella AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="41c86-p115">If set, Address Book Server does not include objects in the AbUserEntry table that do not have this value for the specified attribute. If both the 0x4000 and 0x8000 flag bits are set on an object, the attribute with the flag bit value set to 0x4000 takes precedence, and the object is excluded from the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c86-239">0x10000</span><span class="sxs-lookup"><span data-stu-id="41c86-239">0x10000</span></span></p></td>
<td><p><span data-ttu-id="41c86-p116">Se impostato, rappresenta un oggetto gruppo. Questo bit di flag viene utilizzato da User Replicator per includere i contatti con l'attributo <strong>groupType</strong>, la cui presenza indica un gruppo (ad esempio, una lista di distribuzione o un gruppo di sicurezza).</span><span class="sxs-lookup"><span data-stu-id="41c86-p116">If set, this represents a group object. User Replicator uses this flag bit to include contacts with the <strong>groupType</strong> attribute whose presence indicates a group (for example, a distribution list or security group).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c86-242">0x20000</span><span class="sxs-lookup"><span data-stu-id="41c86-242">0x20000</span></span></p></td>
<td><p><span data-ttu-id="41c86-243">Se impostato, questo bit di flag viene utilizzato da User Replicator per includere questo attributo nei file del server della Rubrica specifici del dispositivo, ovvero file con estensione dabs.</span><span class="sxs-lookup"><span data-stu-id="41c86-243">If set, User Replicator uses this flag bit to include this attribute in device-specific Address Book Server files (that is, files with a .dabs extension).</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="41c86-244">Nelle versioni precedenti di Lync Server, quando si applicava una modifica ad Active Directory, l'amministratore sarebbe stato tenuto a eseguire i cmdlet **Update-CSUserDatabase** e **Update-CSAddressBook** di Windows PowerShell per rendere permanenti le modifiche apportate al database utente di Lync Server e al database di RTCab.</span><span class="sxs-lookup"><span data-stu-id="41c86-244">In previous versions of Lync Server, when applying a change to Active Directory, the administrator would be required to run **Update -CSUserDatabase** and **Update –CSAddressBook** Windows PowerShell cmdlets to persist the change to the Lync Server user database and RTCab database immediately.</span></span> <span data-ttu-id="41c86-245">In Lync Server 2013, Lync Server User Replicator rileverà le modifiche da Active Directory e aggiornerà il database degli utenti di Lync Server in base a un intervallo configurato.</span><span class="sxs-lookup"><span data-stu-id="41c86-245">In Lync Server 2013, Lync Server User Replicator will pick up the changes from Active Directory and update the Lync Server user database based on a configured interval.</span></span> <span data-ttu-id="41c86-246">Lync Server User Replicator propagherà rapidamente le modifiche apportate al database di RTCab senza che l'amministratore debba eseguire Update-CSAddressBook.</span><span class="sxs-lookup"><span data-stu-id="41c86-246">Lync Server User Replicator will also propagate the changes to the RTCab database quickly without the administrator having to run Update-CSAddressBook.</span></span> <span data-ttu-id="41c86-247">Se la query Web della Rubrica è abilitata, le modifiche verranno applicate ai risultati della ricerca da parte dei client Lync.</span><span class="sxs-lookup"><span data-stu-id="41c86-247">If Address Book Web query is enabled, then the changes will be reflected in search results by Lync clients.</span></span> <span data-ttu-id="41c86-248">Gli amministratori devono solo eseguire Update-CSAddressBook se il download dei file della Rubrica è abilitato.</span><span class="sxs-lookup"><span data-stu-id="41c86-248">Administrators will only need to run Update -CSAddressBook if the Address Book file download is enabled.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="41c86-249">Per impostazione predefinita, Lync Server User Replicator viene eseguito automaticamente ogni 5 minuti.</span><span class="sxs-lookup"><span data-stu-id="41c86-249">By default Lync Server User Replicator runs automatically every 5 minutes.</span></span> <span data-ttu-id="41c86-250">È possibile configurare questo intervallo utilizzando set-CSUserReplicatorConfiguration-ReplicationCycleInterval &lt; &gt;.</span><span class="sxs-lookup"><span data-stu-id="41c86-250">You can configure this interval by using Set -CSUserReplicatorConfiguration -ReplicationCycleInterval &lt;&gt;.</span></span>



</div>

</div>

<div>

## <a name="filtering-the-address-book"></a><span data-ttu-id="41c86-251">Filtro della Rubrica</span><span class="sxs-lookup"><span data-stu-id="41c86-251">Filtering the Address Book</span></span>

<span data-ttu-id="41c86-252">Gli utenti inseriti nei file del server della rubrica possono essere controllati in base a determinati attributi di servizi di dominio Active Directory elencati nella tabella AbAttribute.</span><span class="sxs-lookup"><span data-stu-id="41c86-252">The users populated in the Address Book Server files can be controlled based on certain Active Directory Domain Services attributes listed in the AbAttribute table.</span></span> <span data-ttu-id="41c86-253">Uno di questi attributi utilizzato per il filtro è \*\*msExchangeHideFromAddressBook \*\*.</span><span class="sxs-lookup"><span data-stu-id="41c86-253">One such attribute used for filtering is the **msExchangeHideFromAddressBook** attribute.</span></span> <span data-ttu-id="41c86-254">Si tratta di un attributo utente aggiunto dallo schema di Exchange.</span><span class="sxs-lookup"><span data-stu-id="41c86-254">This is a user attribute added by the Exchange schema.</span></span> <span data-ttu-id="41c86-255">Se il valore di questo attributo è TRUE, questo attributo viene utilizzato da Exchange Server per nascondere il contatto dall'elenco indirizzi globale di Outlook.</span><span class="sxs-lookup"><span data-stu-id="41c86-255">If the value of this attribute is TRUE, Exchange Server uses this attribute to hide the contact from the Outlook Global Address List (GAL).</span></span> <span data-ttu-id="41c86-256">Analogamente, se il valore di questo attributo è TRUE, tale utente non viene incluso da User Replicator nella tabella AbUserEntry e l'utente non sarà presente nei file del server della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="41c86-256">Similarly, if the value of this attribute is TRUE, User Replicator does not include that user in the AbUserEntry table and this user will not be in the Address Book Server files.</span></span>

<span data-ttu-id="41c86-p120">È possibile utilizzare alcuni bit di flag per definire un filtro da utilizzare per gli attributi del server della Rubrica. La presenza di alcuni bit di flag consente, ad esempio, di identificare un attributo come attributo di inclusione o di esclusione. User Replicator consente di escludere tramite filtro i contatti che contengono un attributo di esclusione e quelli che non contengono un attributo di inclusione.</span><span class="sxs-lookup"><span data-stu-id="41c86-p120">You can use some flag bits to define a filter to use on Address Book Server attributes. For example, the presence of certain flag bits can identify an attribute as an include attribute or an exclude attribute. User Replicator filters out contacts that contain an exclude attribute and filters out contains that do not contain an include attribute.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="41c86-260">Per ulteriori informazioni sul filtraggio della Rubrica, vedere <A href="https://technet.microsoft.com/library/gg415643(v=ocs.15)">cmdlet del server della Rubrica in Lync server 2013</A>e <A href="https://go.microsoft.com/fwlink/?linkid=330430">filtrare la rubrica di Lync 2013</A></span><span class="sxs-lookup"><span data-stu-id="41c86-260">For more information about filtering the Address Book, see <A href="https://technet.microsoft.com/library/gg415643(v=ocs.15)">Address Book Server cmdlets in Lync Server 2013</A>, and <A href="https://go.microsoft.com/fwlink/?linkid=330430">Filter Lync 2013 address book</A></span></span>



</div>

<span data-ttu-id="41c86-p121">Attualmente, sono disponibili tre diversi filtri, elencati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="41c86-p121">Currently, there are three different filters. The following table lists these filters.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="41c86-263">Attributo</span><span class="sxs-lookup"><span data-stu-id="41c86-263">Attribute</span></span></th>
<th><span data-ttu-id="41c86-264">Descrizione</span><span class="sxs-lookup"><span data-stu-id="41c86-264">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41c86-265">0x800</span><span class="sxs-lookup"><span data-stu-id="41c86-265">0x800</span></span></p></td>
<td><p><span data-ttu-id="41c86-p122">Se impostato, identifica un attributo obbligatorio per un contatto. Questo bit di flag viene utilizzato da User Replicator per escludere tramite filtro i contatti che non includono almeno un attributo obbligatorio. OuPathId è un attributo obbligatorio, che è sempre impostato. È pertanto necessario che sia impostato almeno un altro degli attributi obbligatori. In caso contrario, il contatto (ovvero con il valore dell'attributo obbligatorio OuPathId) non sarà scritto nel database. Se, ad esempio, <strong>telephoneNumber</strong> e <strong>homePhone</strong> sono definiti come attributi obbligatori, solo i contatti che dispongono di almeno uno di questi attributi vengono scritti nel database.</span><span class="sxs-lookup"><span data-stu-id="41c86-p122">If set, this identifies a required attribute for a contact. User Replicator uses this flag bit to filter out contacts that do not contain at least one required attribute. The OuPathId is a required attribute, which is always set. So at least one of other required attributes should be set. Otherwise, contact (that is, with value of required attribute OuPathId) will still not be written to database. For example, if <strong>telephoneNumber</strong> and <strong>homePhone</strong> are defined as required attributes, only the contacts that have at least one of these attributes are written to the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c86-272">0x4000</span><span class="sxs-lookup"><span data-stu-id="41c86-272">0x4000</span></span></p></td>
<td><p><span data-ttu-id="41c86-p123">Se impostato, identifica un attributo di esclusione. Questo bit di flag viene utilizzato da User Replicator per escludere tramite filtro i contatti che contengono questo attributo. Se, ad esempio, <strong>msRTCSIP-PrimaryUserAddress</strong> è definito come attributo di esclusione, i contatti che dispongono di questo attributo non vengono scritti nel database.</span><span class="sxs-lookup"><span data-stu-id="41c86-p123">If set, this identifies an exclude attribute. User Replicator uses this flag bit to filter out contacts that contain this attribute. For example, if <strong>msRTCSIP-PrimaryUserAddress</strong> is defined as an exclude attribute, contacts that have this attribute are not written to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c86-276">0x8000</span><span class="sxs-lookup"><span data-stu-id="41c86-276">0x8000</span></span></p></td>
<td><p><span data-ttu-id="41c86-p124">Se impostato, identifica un attributo di inclusione. Questo bit di flag viene utilizzato da User Replicator per escludere tramite filtro i contatti che non contengono questo attributo. Se, ad esempio, <strong>msRTCSIP-PrimaryUserAddress</strong> è definito come attributo di inclusione, solo i contatti che dispongono di questo attributo vengono scritti nel database.</span><span class="sxs-lookup"><span data-stu-id="41c86-p124">If set, this identifies an include attribute. User Replicator uses this flag bit to filter out contacts that do not contain this attribute. For example, if <strong>msRTCSIP-PrimaryUserAddress</strong> is defined as an include attribute, only the contacts that have this attribute are written to the database.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="41c86-280">Se vengono impostati entrambi i bit di flag, 0x4000 (attributo di esclusione) e 0x8000 (attributo di inclusione), il bit 0x4000 ha la precedenza su 0x8000 e il contatto viene escluso.</span><span class="sxs-lookup"><span data-stu-id="41c86-280">If both the 0x4000 (exclude attribute) and 0x8000 (include attribute) flag bits are set, the 0x4000 bit overrides the 0x8000 bit and the contact is excluded.</span></span>



</div>

<span data-ttu-id="41c86-p125">Sebbene sia possibile filtrare la Rubrica per includere solo determinati utenti, la limitazione delle voci non implica una limitazione della possibilità da parte di altri utenti di contattare gli utenti esclusi tramite filtro o di visualizzare il loro stato presenza. Gli utenti possono sempre trovare gli utenti non inclusi nella Rubrica, inviare loro manualmente messaggi istantanei o avviare manualmente chiamate verso tali utenti, immettendo il nome di accesso completo dell'utente. Le informazioni sul contatto per un utente sono inoltre disponibili anche in Outlook.</span><span class="sxs-lookup"><span data-stu-id="41c86-p125">Although you can filter the Address Book to include only certain users, limiting entries does not limit other users' ability to contact the filtered users or to see their presence status. Users can always find, manually send instant messages, or manually initiate calls to users not in the Address Book by entering a user's complete sign-in name. Also, contact information for a user could also be found in Outlook.</span></span>

<span data-ttu-id="41c86-284">Anche se i record dei contatti completi nei file della rubrica consentono di utilizzare Lync Server per avviare messaggi di posta elettronica, telefonici o VoIP aziendale (ovvero se VoIP aziendale è abilitato sul server) con gli utenti non configurati per l'avvio della sessione Protocol (SIP), alcune organizzazioni preferiscono includere solo gli utenti abilitati per SIP nelle voci del server della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="41c86-284">While having full contact records in the Address Book files enables you to use Lync Server to initiate email, telephone, or Enterprise Voice calls (that is, if Enterprise Voice is enabled on the server) with users that are not configured for Session Initiation Protocol (SIP), some organizations prefer to include only SIP-enabled users in their Address Book Server entries.</span></span> <span data-ttu-id="41c86-285">È possibile filtrare la Rubrica per includere solo gli utenti abilitati per SIP cancellando il bit 0x800 nella colonna **Flags** per gli attributi obbligatori seguenti: **mailNickname**, **telephoneNumber**, **homePhone** e **mobile**.</span><span class="sxs-lookup"><span data-stu-id="41c86-285">You can filter the Address Book to include only SIP-enabled users by clearing the 0x800 bit in the **Flags** column of the following required attributes: **mailNickname**, **telephoneNumber**, **homePhone**, and **mobile**.</span></span> <span data-ttu-id="41c86-286">È inoltre possibile filtrare la Rubrica per includere solo utenti abilitati per SIP impostando 0x8000 (attributo di inclusione) nella colonna **Flags** dell'attributo **msRTCSIP-PrimaryUserAddress**.</span><span class="sxs-lookup"><span data-stu-id="41c86-286">You can also filter the Address Book to include only SIP-enabled users by setting the 0x8000 (include attribute) in the **Flags** column of the **msRTCSIP-PrimaryUserAddress** attribute.</span></span> <span data-ttu-id="41c86-287">In questo modo vengono inoltre esclusi gli account del servizio dai file della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="41c86-287">This also helps to exclude service accounts from the Address Book files.</span></span>

<span data-ttu-id="41c86-288">Dopo aver modificato la tabella AbAttribute, è possibile aggiornare i dati nella tabella AbUserEntry eseguendo il cmdlet **Update-CsUserDatabase**.</span><span class="sxs-lookup"><span data-stu-id="41c86-288">After you modify the AbAttribute table, you can refresh the data in the AbUserEntry table by running the cmdlet **Update-CsUserDatabase** command.</span></span> <span data-ttu-id="41c86-289">Al termine della replica di User Replicator, è possibile aggiornare il file dell'archivio file del server della Rubrica eseguendo manualmente il cmdlet **UpdateCsAddressBook**.</span><span class="sxs-lookup"><span data-stu-id="41c86-289">After UR replication completes, you can update the file in the Address Book Server file store by manually running the cmdlet **UpdateCsAddressBook** command.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="41c86-290">Il front end server che il server della Rubrica è posizionato non è configurabile amministrativamente.</span><span class="sxs-lookup"><span data-stu-id="41c86-290">The Front End Server that the Address Book Server is placed is not administratively configurable.</span></span> <span data-ttu-id="41c86-291">Uno viene scelto durante la distribuzione, in genere il primo front end server distribuito.</span><span class="sxs-lookup"><span data-stu-id="41c86-291">One is chosen during deployment—typically, the first Front End Server deployed.</span></span> <span data-ttu-id="41c86-292">In caso di errore, il servizio Rubrica verrà spostato in un altro front end server e non richiede alcuna attenzione amministrativa.</span><span class="sxs-lookup"><span data-stu-id="41c86-292">In the event of failure, the Address Book Service will move to another Front End Server, and requires no administrative attention.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="41c86-293">Se l'infrastruttura è stata consolidata o modificata in altro modo da una distribuzione a più foreste o da una distribuzione padre/figlio, ad esempio il consolidamento dell'infrastruttura prima di passare a Lync Server, potrebbe essere possibile che il download del servizio Rubrica e la query Web della Rubrica non siano in grado di soddisfare alcuni utenti.</span><span class="sxs-lookup"><span data-stu-id="41c86-293">If you have consolidated or otherwise modified your infrastructure from a multi-forest deployment or a parent/child deployment (such as consolidating your infrastructure before moving to Lync Server), you may find that the Address Book service download and the Address Book Web Query fails for some users.</span></span> <span data-ttu-id="41c86-294">In una distribuzione con più domini o foreste, l'attributo <STRONG>MsRTCSIP-OriginatorSid</STRONG> viene popolato negli oggetti utente in cui si presenta il problema.</span><span class="sxs-lookup"><span data-stu-id="41c86-294">When in a deployment that had multiple domains or forests, the attribute <STRONG>MsRTCSIP-OriginatorSid</STRONG> is populated on the user objects that are exhibiting the issue.</span></span> <span data-ttu-id="41c86-295">Per risolvere il problema, l'attributo <STRONG>MsRTCSIP-OriginatorSid</STRONG> deve essere impostato su NULL in questi oggetti.</span><span class="sxs-lookup"><span data-stu-id="41c86-295">The <STRONG>MsRTCSIP-OriginatorSid</STRONG> attribute must be set to NULL on these objects to resolve the issue.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

