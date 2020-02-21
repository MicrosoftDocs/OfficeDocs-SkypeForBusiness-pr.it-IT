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
ms.openlocfilehash: e68dbe4db6ee9ac6b9bd758b23a575089019f6c7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a><span data-ttu-id="a2e7c-102">Eseguire la migrazione della rubrica</span><span class="sxs-lookup"><span data-stu-id="a2e7c-102">Migrate Address Book</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2e7c-103">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="a2e7c-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="a2e7c-104">**Per eseguire la migrazione delle regole di normalizzazione personalizzate della Rubrica**</span><span class="sxs-lookup"><span data-stu-id="a2e7c-104">**To migrate Address Book customized normalization rules**</span></span>

1.  <span data-ttu-id="a2e7c-105">Individuare il file\_\_rules\_. txt del numero di telefono\_della società nella radice della cartella condivisa della Rubrica e copiarlo nella radice della cartella condivisa della Rubrica nel pool pilota di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a2e7c-105">Find the Company\_Phone\_Number\_Normalization\_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Lync Server 2013 pilot pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a2e7c-106">Le regole di normalizzazione della Rubrica di esempio sono state installate nella directory dei file dei componenti Web del Servizio Rubrica.</span><span class="sxs-lookup"><span data-stu-id="a2e7c-106">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="a2e7c-107">Il percorso è <STRONG>$installedDriveLetter:\Programmi\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="a2e7c-107">The path is <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>.</span></span> <span data-ttu-id="a2e7c-108">Questo file può essere copiato e rinominato come &nbsp; <STRONG>Company_Phone_Number_Normalization_Rules. txt</STRONG> &nbsp;nella directory radice della cartella condivisa della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="a2e7c-108">This file can be copied and renamed as &nbsp;<STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp;to the address book shared folder’s root directory.</span></span> <span data-ttu-id="a2e7c-109">Ad esempio, la rubrica condivisa in <STRONG>$serverX</STRONG>,&nbsp;il percorso sarà analogo al seguente: <STRONG> \\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="a2e7c-109">For example, the address book shared in <STRONG>$serverX</STRONG>,&nbsp;the path will be similar to: <STRONG>\\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span></span>

    
    </div>

2.  <span data-ttu-id="a2e7c-110">Utilizzare un editor di testo, ad esempio Blocco note, per aprire\_il\_file\_\_Rules. txt del numero di telefono dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="a2e7c-110">Use a text editor, such as Notepad, to open the Company\_Phone\_Number\_Normalization\_Rules.txt file.</span></span>

3.  <span data-ttu-id="a2e7c-111">Alcuni tipi di voci non funzioneranno correttamente in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a2e7c-111">Certain types of entries will not work correctly in Lync Server 2013.</span></span> <span data-ttu-id="a2e7c-112">Cercare all'interno del file i tipi di voci descritti in questo passaggio, modificarli secondo necessità e salvare le modifiche nella cartella condivisa della Rubrica all'interno del pool pilota.</span><span class="sxs-lookup"><span data-stu-id="a2e7c-112">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>
    
    <span data-ttu-id="a2e7c-p103">Le stringhe che includono spazi o caratteri di punteggiatura necessari provocano un errore nelle regole di normalizzazione poiché tali caratteri vengono rimossi dalla stringa utilizzata come input nelle regole di normalizzazione. Se sono presenti stringhe che includono spazi o caratteri di punteggiatura necessari, è necessario modificare le stringhe. La stringa seguente, ad esempio, genererà un errore nelle regola di normalizzazione:</span><span class="sxs-lookup"><span data-stu-id="a2e7c-p103">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules. If you have strings that include required whitespace or punctuation, you need to modify the strings. For example, the following string would cause the normalization rule to fail:</span></span>
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    <span data-ttu-id="a2e7c-116">La stringa seguente non causerebbe alcun errore della regola di normalizzazione:</span><span class="sxs-lookup"><span data-stu-id="a2e7c-116">The following string would not cause the normalization rule to fail:</span></span>
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<span> </span>

</div>

</div>

</div>

