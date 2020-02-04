---
title: Eseguire la migrazione della rubrica
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Address Book
ms:assetid: b6e000ce-8b2e-460c-8a8b-000254b9d778
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205198(v=OCS.15)
ms:contentKeyID: 48185218
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2c904a122f781da08c92c6b1123cfeb1944dd2e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765274"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a><span data-ttu-id="5ddef-102">Eseguire la migrazione della rubrica</span><span class="sxs-lookup"><span data-stu-id="5ddef-102">Migrate Address Book</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ddef-103">_**Argomento Ultima modifica:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="5ddef-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="5ddef-104">**Per eseguire la migrazione delle regole di normalizzazione personalizzate della Rubrica**</span><span class="sxs-lookup"><span data-stu-id="5ddef-104">**To migrate Address Book customized normalization rules**</span></span>

1.  <span data-ttu-id="5ddef-105">Individuare il file\_\_rules\_. txt del numero di telefono\_aziendale nella radice della cartella condivisa della Rubrica e copiarlo nella radice della cartella condivisa rubrica nel pool di piloti di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5ddef-105">Find the Company\_Phone\_Number\_Normalization\_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Lync Server 2013 pilot pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5ddef-106">Le regole di normalizzazione della Rubrica di esempio sono state installate nella directory dei file del componente Web ABS.</span><span class="sxs-lookup"><span data-stu-id="5ddef-106">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="5ddef-107">Il percorso è <STRONG>$installedDriveLetter: \Programmi\microsoft Lync Server 2013 \ Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules. txt,</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="5ddef-107">The path is <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>.</span></span> <span data-ttu-id="5ddef-108">Questo file può essere copiato e rinominato come &nbsp; <STRONG>Company_Phone_Number_Normalization_Rules. txt</STRONG> &nbsp;nella directory radice della cartella condivisa della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="5ddef-108">This file can be copied and renamed as &nbsp;<STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp;to the address book shared folder’s root directory.</span></span> <span data-ttu-id="5ddef-109">Ad esempio, la rubrica condivisa in <STRONG>$serverX</STRONG>,&nbsp;il percorso sarà simile a: <STRONG> \\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="5ddef-109">For example, the address book shared in <STRONG>$serverX</STRONG>,&nbsp;the path will be similar to: <STRONG>\\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span></span>

    
    </div>

2.  <span data-ttu-id="5ddef-110">Usare un editor di testo, ad esempio Blocco note, per aprire\_il\_file\_regole\_di normalizzazione del numero di telefono aziendale. txt.</span><span class="sxs-lookup"><span data-stu-id="5ddef-110">Use a text editor, such as Notepad, to open the Company\_Phone\_Number\_Normalization\_Rules.txt file.</span></span>

3.  <span data-ttu-id="5ddef-111">Alcuni tipi di voci non funzionano correttamente in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5ddef-111">Certain types of entries will not work correctly in Lync Server 2013.</span></span> <span data-ttu-id="5ddef-112">Esaminare il file per i tipi di voci descritti in questo passaggio, modificarli come necessario e salvare le modifiche apportate alla cartella condivisa Rubrica nel pool di piloti.</span><span class="sxs-lookup"><span data-stu-id="5ddef-112">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>
    
    <span data-ttu-id="5ddef-113">Le stringhe che includono gli spazi vuoti o la punteggiatura necessari causano l'errore delle regole di normalizzazione perché questi caratteri vengono rimossi dalla stringa che viene immessa nelle regole di normalizzazione.</span><span class="sxs-lookup"><span data-stu-id="5ddef-113">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="5ddef-114">Se sono presenti stringhe che includono spazi vuoti o segni di punteggiatura necessari, è necessario modificare le stringhe.</span><span class="sxs-lookup"><span data-stu-id="5ddef-114">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="5ddef-115">Ad esempio, la stringa seguente causerà l'errore della regola di normalizzazione:</span><span class="sxs-lookup"><span data-stu-id="5ddef-115">For example, the following string would cause the normalization rule to fail:</span></span>
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    <span data-ttu-id="5ddef-116">La stringa seguente non provocherebbe l'errore della regola di normalizzazione:</span><span class="sxs-lookup"><span data-stu-id="5ddef-116">The following string would not cause the normalization rule to fail:</span></span>
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<span> </span>

</div>

</div>

</div>

