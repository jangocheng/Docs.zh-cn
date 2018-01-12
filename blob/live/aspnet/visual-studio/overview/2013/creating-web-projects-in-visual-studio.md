---
uid: visual-studio/overview/2013/creating-web-projects-in-visual-studio
title: "创建 Visual Studio 2013 中的 ASP.NET Web 项目 |Microsoft 文档"
author: tdykstra
description: "本主题介绍在使用此处更新 3 的 Visual Studio 2013 中创建 ASP.NET web 项目的选项是一些用于 web 开发 c 的新增功能..."
ms.author: aspnetcontent
manager: wpickett
ms.date: 12/01/2014
ms.topic: article
ms.assetid: 61941e64-0c0d-4996-9270-cb8ccfd0cabc
ms.technology: 
ms.prod: .net-framework
msc.legacyurl: /visual-studio/overview/2013/creating-web-projects-in-visual-studio
msc.type: authoredcontent
ms.openlocfilehash: 96960ef56b1206374458dbbba4befffaa83c1624
ms.sourcegitcommit: 9a9483aceb34591c97451997036a9120c3fe2baf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2017
---
<a name="creating-aspnet-web-projects-in-visual-studio-2013"></a><span data-ttu-id="50896-103">在 Visual Studio 2013 中创建 ASP.NET Web 项目</span><span class="sxs-lookup"><span data-stu-id="50896-103">Creating ASP.NET Web Projects in Visual Studio 2013</span></span>
====================
<span data-ttu-id="50896-104">通过[Tom Dykstra](https://github.com/tdykstra)</span><span class="sxs-lookup"><span data-stu-id="50896-104">by [Tom Dykstra](https://github.com/tdykstra)</span></span>

> <span data-ttu-id="50896-105">本主题说明了在 Visual Studio 2013 Update 3 中创建 ASP.NET web 项目的选项</span><span class="sxs-lookup"><span data-stu-id="50896-105">This topic explains the options for creating ASP.NET web projects in Visual Studio 2013 with Update 3</span></span>
> 
> <span data-ttu-id="50896-106">下面是一些用于相对于早期版本的 Visual Studio 的 web 开发的新增功能：</span><span class="sxs-lookup"><span data-stu-id="50896-106">Here are some of the new features for web development compared to earlier versions of Visual Studio:</span></span>
> 
> - <span data-ttu-id="50896-107">用于创建一个简单的 UI 项目提供[支持多个 ASP.NET 框架](#add)（Web 窗体、 MVC 和 Web API）。</span><span class="sxs-lookup"><span data-stu-id="50896-107">A simple UI for creating projects that offer [support for multiple ASP.NET frameworks](#add) (Web Forms, MVC, and Web API).</span></span>
> - <span data-ttu-id="50896-108">[ASP.NET 标识](#indauth)，新的 ASP.NET 成员资格系统中所有的 ASP.NET 框架和工作原理相同适用于 web 托管非 IIS 的软件。</span><span class="sxs-lookup"><span data-stu-id="50896-108">[ASP.NET Identity](#indauth), a new ASP.NET membership system that works the same in all ASP.NET frameworks and works with web hosting software other than IIS.</span></span>
> - <span data-ttu-id="50896-109">使用[Bootstrap](#bootstrap)提供响应式设计和主题功能。</span><span class="sxs-lookup"><span data-stu-id="50896-109">The use of [Bootstrap](#bootstrap) to provide responsive design and theming capabilities.</span></span>
> - <span data-ttu-id="50896-110">用于仅为 MVC，如提供的 Web 窗体的新功能[自动测试项目创建](#testproj)和[Intranet 站点模板](#winauth)。</span><span class="sxs-lookup"><span data-stu-id="50896-110">New features for Web Forms that used to be offered only for MVC, such as [automatic test project creation](#testproj) and an [Intranet site template](#winauth).</span></span>
> 
> <span data-ttu-id="50896-111">有关如何为 Azure 云服务或 Azure 移动服务中创建 web 项目的信息，请参阅[Azure 云服务和 ASP.NET 入门](https://azure.microsoft.com/en-us/documentation/articles/cloud-services-dotnet-get-started/)和[使用 Azure 移动服务.NET 创建排行榜应用程序后端](https://azure.microsoft.com/en-us/documentation/articles/mobile-services-dotnet-backend-windows-store-dotnet-leaderboard/)。</span><span class="sxs-lookup"><span data-stu-id="50896-111">For information about how to create web projects for Azure Cloud Services or Azure Mobile Services, see [Get Started with Azure Cloud Services and ASP.NET](https://azure.microsoft.com/en-us/documentation/articles/cloud-services-dotnet-get-started/) and [Creating a Leaderboard App with Azure Mobile Services .NET Backend](https://azure.microsoft.com/en-us/documentation/articles/mobile-services-dotnet-backend-windows-store-dotnet-leaderboard/).</span></span>


<a id="prerequisites"></a>
## <a name="prerequisites"></a><span data-ttu-id="50896-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="50896-112">Prerequisites</span></span>

<span data-ttu-id="50896-113">本文适用于[Visual Studio 2013](https://go.microsoft.com/fwlink/?LinkId=306566)与[Update 3](https://go.microsoft.com/fwlink/?linkid=397827&amp;clcid=0x409)安装。</span><span class="sxs-lookup"><span data-stu-id="50896-113">This article applies to [Visual Studio 2013](https://go.microsoft.com/fwlink/?LinkId=306566) with [Update 3](https://go.microsoft.com/fwlink/?linkid=397827&amp;clcid=0x409) installed.</span></span>

<a id="wap"></a>
## <a name="web-application-projects-versus-web-site-projects"></a><span data-ttu-id="50896-114">与网站项目的 web 应用程序项目</span><span class="sxs-lookup"><span data-stu-id="50896-114">Web application projects versus web site projects</span></span>

<span data-ttu-id="50896-115">ASP.NET 为你提供了两种类型的 web 项目之间进行选择： *web 应用程序项目*和*网站项目*。</span><span class="sxs-lookup"><span data-stu-id="50896-115">ASP.NET gives you a choice between two kinds of web projects: *web application projects* and *web site projects*.</span></span> <span data-ttu-id="50896-116">我们建议对于新开发，web 应用程序项目，并且本文仅适用于 web 应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="50896-116">We recommend web application projects for new development, and this article applies only to web application projects.</span></span> <span data-ttu-id="50896-117">有关详细信息，请参阅[Web 应用程序项目与 Visual Studio 中的网站项目](https://msdn.microsoft.com/en-us/library/dd547590(v=vs.120).aspx)MSDN 网站上的。</span><span class="sxs-lookup"><span data-stu-id="50896-117">For more information, see [Web Application Projects versus Web Site Projects in Visual Studio](https://msdn.microsoft.com/en-us/library/dd547590(v=vs.120).aspx) on the MSDN site.</span></span>

<a id="overview"></a>
## <a name="overview-of-web-application-project-creation"></a><span data-ttu-id="50896-118">Web 应用程序项目创建的概述</span><span class="sxs-lookup"><span data-stu-id="50896-118">Overview of web application project creation</span></span>

<span data-ttu-id="50896-119">以下步骤演示了如何创建 web 项目：</span><span class="sxs-lookup"><span data-stu-id="50896-119">The following steps show how to create a web project:</span></span>

1. <span data-ttu-id="50896-120">单击**新项目**中**启动**页或在**文件**菜单。</span><span class="sxs-lookup"><span data-stu-id="50896-120">Click **New Project** in the **Start** page or in the **File** menu.</span></span>
2. <span data-ttu-id="50896-121">在**新项目**对话框中，单击**Web**的左窗格中和**ASP.NET Web 应用程序**在中间窗格中。</span><span class="sxs-lookup"><span data-stu-id="50896-121">In the **New Project** dialog, click **Web** in the left pane and **ASP.NET Web Application** in the middle pane.</span></span>

    ![“新建项目”对话框](creating-web-projects-in-visual-studio/_static/image1.png)

    <span data-ttu-id="50896-123">你可以选择**云**在左窗格中创建[Azure 云服务](https://docs.microsoft.com/azure/cloud-services/cloud-services-how-to-create-deploy)， [Azure 移动服务](https://msdn.microsoft.com/en-us/library/windows/apps/dn629482.aspx)，或[Azure web 作业](https://azure.microsoft.com/en-us/documentation/articles/web-sites-dotnet-deploy-webjobs)。</span><span class="sxs-lookup"><span data-stu-id="50896-123">You can choose **Cloud** in the left pane to create an [Azure Cloud Service](https://docs.microsoft.com/azure/cloud-services/cloud-services-how-to-create-deploy), [Azure Mobile Service](https://msdn.microsoft.com/en-us/library/windows/apps/dn629482.aspx), or [Azure WebJob](https://azure.microsoft.com/en-us/documentation/articles/web-sites-dotnet-deploy-webjobs).</span></span> <span data-ttu-id="50896-124">本主题并未涵盖这些模板。</span><span class="sxs-lookup"><span data-stu-id="50896-124">This topic doesn't cover those templates.</span></span>
3. <span data-ttu-id="50896-125">在右窗格中，单击**向项目添加 Application Insights**复选框，如果你希望运行状况和使用情况监视你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="50896-125">In the right pane, click the **Add Application Insights to Project** check box if you want health and usage monitoring for your application.</span></span> <span data-ttu-id="50896-126">有关详细信息，请参阅[监视 web 应用程序性能的](https://azure.microsoft.com/en-us/documentation/articles/app-insights-web-monitor-performance/)。</span><span class="sxs-lookup"><span data-stu-id="50896-126">For more information, see [Monitor performance in web applications](https://azure.microsoft.com/en-us/documentation/articles/app-insights-web-monitor-performance/).</span></span>
4. <span data-ttu-id="50896-127">指定项目**名称**，**位置**，和其他选项，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="50896-127">Specify project **Name**, **Location**, and other options, and then click **OK**.</span></span>

    <span data-ttu-id="50896-128">**新建 ASP.NET 项目**此时将显示对话框。</span><span class="sxs-lookup"><span data-stu-id="50896-128">The **New ASP.NET Project** dialog appears.</span></span>

    ![“新建项目”对话框](creating-web-projects-in-visual-studio/_static/image2.png)
5. <span data-ttu-id="50896-130">单击模板。</span><span class="sxs-lookup"><span data-stu-id="50896-130">Click a template.</span></span>

    ![选择模板](creating-web-projects-in-visual-studio/_static/image3.png)
6. <span data-ttu-id="50896-132">如果你想要添加未包含模板中的其他框架的支持，请单击相应的复选框。</span><span class="sxs-lookup"><span data-stu-id="50896-132">If you want to add support for additional frameworks not included in the template, click the appropriate check box.</span></span> <span data-ttu-id="50896-133">（在示例中所示，你无法 MVC 和/或 Web API 向项目中添加 Web 窗体。）</span><span class="sxs-lookup"><span data-stu-id="50896-133">(In the example shown, you could add MVC and/or Web API to a Web Forms project.)</span></span>

    ![添加框架](creating-web-projects-in-visual-studio/_static/image4.png)
7. <a id="testproj"></a><span data-ttu-id="50896-135">如果你想要添加单元测试项目，请单击**添加单元测试**。</span><span class="sxs-lookup"><span data-stu-id="50896-135">If you want to add a unit test project, click **Add unit tests**.</span></span>

    ![添加单元测试](creating-web-projects-in-visual-studio/_static/image5.png)
8. <span data-ttu-id="50896-137">如果希望比默认情况下所提供的模板的不同的身份验证方法，请单击**更改身份验证**。</span><span class="sxs-lookup"><span data-stu-id="50896-137">If you want a different authentication method than what the template provides by default, click **Change Authentication**.</span></span>

    ![配置身份验证按钮](creating-web-projects-in-visual-studio/_static/image6.png)

    ![配置身份验证对话框](creating-web-projects-in-visual-studio/_static/image7.png)

<a id="azurenewproj"></a>
### <a name="create-a-web-app-or-virtual-machine-in-azure"></a><span data-ttu-id="50896-140">在 Azure 中创建 web 应用程序或虚拟机</span><span class="sxs-lookup"><span data-stu-id="50896-140">Create a web app or virtual machine in Azure</span></span>

<span data-ttu-id="50896-141">Visual Studio 包含使其易于使用的 Azure 服务以托管 web 应用程序的功能。</span><span class="sxs-lookup"><span data-stu-id="50896-141">Visual Studio includes features that make it easy to work with Azure services for hosting web applications.</span></span> <span data-ttu-id="50896-142">例如，可以直接从 Visual Studio IDE 执行所有以下操作：</span><span class="sxs-lookup"><span data-stu-id="50896-142">For example, you can do all of the following right from the Visual Studio IDE:</span></span>

- <span data-ttu-id="50896-143">创建和管理 web 应用程序或使你的应用程序可通过 Internet 的虚拟机。</span><span class="sxs-lookup"><span data-stu-id="50896-143">Create and manage web apps or virtual machines that make your application available over the Internet.</span></span>
- <span data-ttu-id="50896-144">查看在云中运行应用程序创建的日志。</span><span class="sxs-lookup"><span data-stu-id="50896-144">View logs created by the application as it runs in the cloud.</span></span>
- <span data-ttu-id="50896-145">在调试模式下远程运行应用程序在云中运行时。</span><span class="sxs-lookup"><span data-stu-id="50896-145">Run in debug mode remotely while the application runs in the cloud.</span></span>
- <span data-ttu-id="50896-146">Viiew 和管理 SQL 数据库之类的其他 Azure 服务。</span><span class="sxs-lookup"><span data-stu-id="50896-146">Viiew and manage other Azure services such as SQL databases.</span></span>

<span data-ttu-id="50896-147">你可以[创建 Azure 帐户](https://www.windowsazure.com/en-us/pricing/free-trial/)免费，包括基本的服务，如 web apps，并且如果你是 MSDN 订阅者可以[激活权益](https://azure.microsoft.com/pricing/member-offers/visual-studio-subscriptions/)，为你提供其他 azure 的月度信用额度服务。</span><span class="sxs-lookup"><span data-stu-id="50896-147">You can [create an Azure account](https://www.windowsazure.com/en-us/pricing/free-trial/) that includes basic services such as web apps for free, and if you are an MSDN subscriber you can [activate benefits](https://azure.microsoft.com/pricing/member-offers/visual-studio-subscriptions/) that give you monthly credits toward additional Azure services.</span></span> 

<span data-ttu-id="50896-148">默认情况下**新建 ASP.NET 项目**对话框中，可以创建 web 应用程序或新的 web 项目的虚拟机。</span><span class="sxs-lookup"><span data-stu-id="50896-148">By default the **New ASP.NET Project** dialog box enables you to create a web app or virtual machine for a new web project.</span></span> <span data-ttu-id="50896-149">如果你不想要创建新的 web 应用程序或虚拟机，清除**在云中托管**复选框。</span><span class="sxs-lookup"><span data-stu-id="50896-149">If you don't want to create a new web app or virtual machine, clear the **Host in the cloud** check box.</span></span>

![创建远程资源](creating-web-projects-in-visual-studio/_static/image8.png)

<span data-ttu-id="50896-151">复选框标题可能**在云中托管**或**创建远程资源**，并在任一情况下效果都是相同。</span><span class="sxs-lookup"><span data-stu-id="50896-151">The check box caption might be **Host in the cloud** or **Create remote resources**, and in either case the effect is the same.</span></span> <span data-ttu-id="50896-152">如果你离开选中此复选框，Visual Studio 创建的 web 应用在 Azure App Service 中默认情况下。</span><span class="sxs-lookup"><span data-stu-id="50896-152">If you leave the check box selected, Visual Studio creates a web app in Azure App Service by default.</span></span> <span data-ttu-id="50896-153">你可以使用下拉框更改，则为**虚拟机**如果你愿意。</span><span class="sxs-lookup"><span data-stu-id="50896-153">You can use the drop-down box to change that to a **Virtual Machine** if you prefer.</span></span> <span data-ttu-id="50896-154">如果你尚未登录到 Azure，将提示你输入 Azure 凭据。</span><span class="sxs-lookup"><span data-stu-id="50896-154">If you're not already signed in to Azure, you're prompted for Azure credentials.</span></span> <span data-ttu-id="50896-155">登录后，对话框中可配置 Visual Studio 将为你的项目创建的资源。</span><span class="sxs-lookup"><span data-stu-id="50896-155">After you sign in, a dialog box enables you to configure the resources that Visual Studio will create for your project.</span></span> <span data-ttu-id="50896-156">下图显示了为 web 应用; 的对话框如果你选择创建虚拟机，将显示不同的选项。</span><span class="sxs-lookup"><span data-stu-id="50896-156">The following illustration shows the dialog for a web app; different options appear if you choose to create a virtual machine.</span></span>

![配置 Azure 应用程序设置](creating-web-projects-in-visual-studio/_static/image9.png)

<span data-ttu-id="50896-158">有关如何使用此过程来创建 Azure 资源的详细信息，请参阅[Azure 和 ASP.NET 入门](https://docs.microsoft.com/azure/app-service-web/app-service-web-get-started-dotnet)和[使用 Visual Studio 创建用于网站的虚拟机](https://azure.microsoft.com/en-us/documentation/articles/virtual-machines-dotnet-create-visual-studio-powershell/)。</span><span class="sxs-lookup"><span data-stu-id="50896-158">For more information about how to use this process for creating Azure resources, see [Get Started with Azure and ASP.NET](https://docs.microsoft.com/azure/app-service-web/app-service-web-get-started-dotnet) and [Creating a virtual machine for a web site with Visual Studio](https://azure.microsoft.com/en-us/documentation/articles/virtual-machines-dotnet-create-visual-studio-powershell/).</span></span>

<span data-ttu-id="50896-159">此文章的剩余部分提供有关可用的模板和其选项的详细信息。</span><span class="sxs-lookup"><span data-stu-id="50896-159">The remainder of this article provides more information about the available templates and their options.</span></span> <span data-ttu-id="50896-160">文章还介绍了 Bootstrap、 布局和主题 framework 了模板中使用。</span><span class="sxs-lookup"><span data-stu-id="50896-160">The article also introduces Bootstrap, the layout and theming framework used in the templates.</span></span>

<a id="vs2013"></a>
## <a name="visual-studio-2013-web-project-templates"></a><span data-ttu-id="50896-161">Visual Studio 2013 Web 项目模板</span><span class="sxs-lookup"><span data-stu-id="50896-161">Visual Studio 2013 Web Project Templates</span></span>

<span data-ttu-id="50896-162">Visual Studio 将使用模板创建 web 项目。</span><span class="sxs-lookup"><span data-stu-id="50896-162">Visual Studio uses templates to create web projects.</span></span> <span data-ttu-id="50896-163">项目模板可以在新项目中创建文件和文件夹，安装 NuGet 包，并为一个基本的工作应用程序提供的示例代码。</span><span class="sxs-lookup"><span data-stu-id="50896-163">A project template can create files and folders in the new project, install NuGet packages, and provide sample code for a rudimentary working application.</span></span> <span data-ttu-id="50896-164">模板实现最新的 web 标准，用于演示如何使用 ASP.NET 技术，以及为你提供跳转的最佳实践开始创建自己的应用程序。</span><span class="sxs-lookup"><span data-stu-id="50896-164">Templates implement the latest web standards and are intended to demonstrate best practices for how to use ASP.NET technologies as well as give you a jump start on creating your own application.</span></span>

<span data-ttu-id="50896-165">Visual Studio 2013 为对面向.NET 4.5 或更高版本的.NET framework 的项目的 web 项目模板提供以下几种选择：</span><span class="sxs-lookup"><span data-stu-id="50896-165">Visual Studio 2013 provides the following choices for web project templates for projects that target .NET 4.5 or later versions of the .NET framework:</span></span>

- [<span data-ttu-id="50896-166">空模板</span><span class="sxs-lookup"><span data-stu-id="50896-166">Empty template</span></span>](#empty)
- [<span data-ttu-id="50896-167">Web 窗体模板</span><span class="sxs-lookup"><span data-stu-id="50896-167">Web Forms template</span></span>](#wf)
- [<span data-ttu-id="50896-168">MVC 模板</span><span class="sxs-lookup"><span data-stu-id="50896-168">MVC template</span></span>](#mvc)
- [<span data-ttu-id="50896-169">Web API 模板</span><span class="sxs-lookup"><span data-stu-id="50896-169">Web API template</span></span>](#webapi)
- [<span data-ttu-id="50896-170">单页面应用程序模板</span><span class="sxs-lookup"><span data-stu-id="50896-170">Single Page Application template</span></span>](#spa)
- [<span data-ttu-id="50896-171">Azure 移动服务模板</span><span class="sxs-lookup"><span data-stu-id="50896-171">Azure Mobile Service template</span></span>](https://azure.microsoft.com/en-us/documentation/articles/mobile-services-dotnet-backend-windows-store-dotnet-leaderboard/)
- [<span data-ttu-id="50896-172">Visual Studio 2012 模板</span><span class="sxs-lookup"><span data-stu-id="50896-172">Visual Studio 2012 Templates</span></span>](#vs2012)

<span data-ttu-id="50896-173">你还可以安装 Visual Studio 扩展，提供[Facebook 模板](#facebook)。</span><span class="sxs-lookup"><span data-stu-id="50896-173">You can also install a Visual Studio extension that provides a [Facebook template](#facebook).</span></span>

<span data-ttu-id="50896-174">有关如何创建.NET 4 为目标的项目的信息，请参阅[Visual Studio 2012 模板](#vs2012)本主题中更高版本。</span><span class="sxs-lookup"><span data-stu-id="50896-174">For information about how to create projects that target .NET 4, see [Visual Studio 2012 Templates](#vs2012) later in this topic.</span></span>

<span data-ttu-id="50896-175">有关如何创建移动客户端的 ASP.NET 应用程序的信息，请参阅[在 ASP.NET 中的移动支持](../../../mobile/index.md)。</span><span class="sxs-lookup"><span data-stu-id="50896-175">For information about how to create ASP.NET applications for mobile clients, see [Mobile Support in ASP.NET](../../../mobile/index.md).</span></span>

<a id="empty"></a>
### <a name="empty-template"></a><span data-ttu-id="50896-176">空模板</span><span class="sxs-lookup"><span data-stu-id="50896-176">Empty Template</span></span>

<span data-ttu-id="50896-177">空模板提供的裸机最小的文件夹和 ASP.NET web 应用程序，如项目文件的文件 (*.csproj*或。*vbproj*) 和一个*Web.config*文件。</span><span class="sxs-lookup"><span data-stu-id="50896-177">The Empty template provides the bare minimum folders and files for an ASP.NET web app, such as a project file (*.csproj* or .*vbproj*) and a *Web.config* file.</span></span> <span data-ttu-id="50896-178">你可以使用下面的复选框添加 Web 窗体、 MVC，和/或 Web API 的支持**将文件夹添加和核心引用：**标签。</span><span class="sxs-lookup"><span data-stu-id="50896-178">You can add support for Web Forms, MVC, and/or Web API by using the check boxes under the **Add folders and core references for:** label.</span></span>

<span data-ttu-id="50896-179">空的模板没有身份验证选项才可用。</span><span class="sxs-lookup"><span data-stu-id="50896-179">For the Empty template no authentication options are available.</span></span> <span data-ttu-id="50896-180">在示例应用程序中实现身份验证功能和空模板不会创建示例应用程序。</span><span class="sxs-lookup"><span data-stu-id="50896-180">Authentication functionality is implemented in sample applications, and the Empty template does not create a sample application.</span></span>

<a id="wf"></a>
### <a name="web-forms-template"></a><span data-ttu-id="50896-181">Web 窗体模板</span><span class="sxs-lookup"><span data-stu-id="50896-181">Web Forms Template</span></span>

<span data-ttu-id="50896-182">框架提供了以下功能，让你快速构建丰富，UI 和数据中的网站的 Web 窗体访问功能：</span><span class="sxs-lookup"><span data-stu-id="50896-182">The Web Forms framework provides the following features that let you rapidly build web sites that are rich in UI and data access features:</span></span>

- <span data-ttu-id="50896-183">Visual Studio 中的所见即所得设计器。</span><span class="sxs-lookup"><span data-stu-id="50896-183">A WYSIWYG designer in Visual Studio.</span></span>
- <span data-ttu-id="50896-184">呈现 HTML 和，你可以通过设置属性和样式自定义的服务器控件。</span><span class="sxs-lookup"><span data-stu-id="50896-184">Server controls that render HTML and that you can customize by setting properties and styles.</span></span>
- <span data-ttu-id="50896-185">丰富多种类型的控件对数据访问和数据显示。</span><span class="sxs-lookup"><span data-stu-id="50896-185">A rich assortment of controls for data access and data display.</span></span>
- <span data-ttu-id="50896-186">公开哪个应用可以您这类程序的事件的事件模型将程序的客户端应用程序，例如 WPF。</span><span class="sxs-lookup"><span data-stu-id="50896-186">An event model that exposes events which you can program like you would program a client application such as WPF.</span></span>
- <span data-ttu-id="50896-187">自动保留的 HTTP 请求之间的状态 （数据）。</span><span class="sxs-lookup"><span data-stu-id="50896-187">Automatic preservation of state (data) between HTTP requests.</span></span>

<span data-ttu-id="50896-188">一般情况下，创建 Web 窗体应用程序需要更少编程的工作量比使用 ASP.NET MVC framework 创建相同的应用程序。</span><span class="sxs-lookup"><span data-stu-id="50896-188">In general, creating a Web Forms application requires less programming effort than creating the same application by using the ASP.NET MVC framework.</span></span> <span data-ttu-id="50896-189">但是，Web 窗体不再仅仅用于快速开发应用程序。</span><span class="sxs-lookup"><span data-stu-id="50896-189">However, Web Forms is not just for rapid application development.</span></span> <span data-ttu-id="50896-190">有许多复杂的商业应用程序和基于 Web 窗体的框架。</span><span class="sxs-lookup"><span data-stu-id="50896-190">There are many complex commercial applications and frameworks built on top of Web Forms.</span></span>

<span data-ttu-id="50896-191">Web 窗体页和页上的控件自动生成大部分发送到浏览器的标记，因为你没有对 ASP.NET MVC 提供的 HTML 细化的控制的类型。</span><span class="sxs-lookup"><span data-stu-id="50896-191">Because a Web Forms page and the controls on the page automatically generate much of the markup that's sent to the browser, you don't have the kind of fine-grained control over the HTML that ASP.NET MVC offers.</span></span> <span data-ttu-id="50896-192">配置页面和控件的声明性模型最大程度减少必须编写，但会隐藏一些 HTML 和 HTTP 的行为的代码量。</span><span class="sxs-lookup"><span data-stu-id="50896-192">The declarative model for configuring pages and controls minimizes the amount of code you have to write but hides some of the behavior of HTML and HTTP.</span></span> <span data-ttu-id="50896-193">例如，它并不总是可以指定控件可能完全生成哪些标记。</span><span class="sxs-lookup"><span data-stu-id="50896-193">For example, it's not always possible to specify exactly what markup might be generated by a control.</span></span>

<span data-ttu-id="50896-194">Web 窗体 framework 不会将自身添加 ASP.NET MVC 为随时到基于模式的开发实践如[测试驱动开发](http://en.wikipedia.org/wiki/Test-driven_development)，[关注点分离](http://en.wikipedia.org/wiki/Separation_of_concerns)，[反向的控件](http://en.wikipedia.org/wiki/Inversion_of_control)，和[依赖关系注入](http://en.wikipedia.org/wiki/Dependency_injection)。</span><span class="sxs-lookup"><span data-stu-id="50896-194">The Web Forms framework doesn't lend itself as readily as ASP.NET MVC to patterns-based development practices such as [test-driven development](http://en.wikipedia.org/wiki/Test-driven_development), [separation of concerns](http://en.wikipedia.org/wiki/Separation_of_concerns), [inversion of control](http://en.wikipedia.org/wiki/Inversion_of_control), and [dependency injection](http://en.wikipedia.org/wiki/Dependency_injection).</span></span> <span data-ttu-id="50896-195">如果你想要编写代码考虑这样一来，你可以;不只是因为它是 ASP.NET MVC framework 中为自动。</span><span class="sxs-lookup"><span data-stu-id="50896-195">If you want to write code factored that way, you can; it's just not as automatic as it is in the ASP.NET MVC framework.</span></span> <span data-ttu-id="50896-196">[ASP.NET Web 窗体 MVP](http://webformsmvp.com/)项目演示一种方法，它方便了问题和可测试性的同时保持生成 Web 窗体提供的快速发展的分离。</span><span class="sxs-lookup"><span data-stu-id="50896-196">The [ASP.NET Web Forms MVP](http://webformsmvp.com/) project shows an approach that facilitates separation of concerns and testability while maintaining the rapid development that Web Forms was built to deliver.</span></span> <span data-ttu-id="50896-197">Microsoft SharePoint 是在 Web 窗体 MVP 基础的。</span><span class="sxs-lookup"><span data-stu-id="50896-197">Microsoft SharePoint is built on Web Forms MVP.</span></span>

<span data-ttu-id="50896-198">Web 窗体模板创建的示例 Web 窗体应用程序使用[Bootstrap](#bootstrap)以提供响应式设计和主题功能。</span><span class="sxs-lookup"><span data-stu-id="50896-198">The Web Forms template creates a sample Web Forms application that uses [Bootstrap](#bootstrap) to provide responsive design and theming features.</span></span> <span data-ttu-id="50896-199">下图显示主页页面。</span><span class="sxs-lookup"><span data-stu-id="50896-199">The following illustration shows the home page.</span></span>

![Web 窗体模板的应用程序主页](creating-web-projects-in-visual-studio/_static/image10.png)

<span data-ttu-id="50896-201">有关 Web 窗体的详细信息，请参阅[ASP.NET Web 窗体](https://asp.net/web-forms)。</span><span class="sxs-lookup"><span data-stu-id="50896-201">For more information about Web Forms, see [ASP.NET Web Forms](https://asp.net/web-forms).</span></span> <span data-ttu-id="50896-202">有关 Web 窗体模板为你的作用的信息，请参阅[生成基本 Web 窗体应用程序使用 Visual Studio 2013](https://blogs.msdn.com/b/webdev/archive/2013/12/19/building-a-basic-web-forms-application-using-visual-studio-2013.aspx)。</span><span class="sxs-lookup"><span data-stu-id="50896-202">For information about what the Web Forms template does for you, see [Building a basic Web Forms application using Visual Studio 2013](https://blogs.msdn.com/b/webdev/archive/2013/12/19/building-a-basic-web-forms-application-using-visual-studio-2013.aspx).</span></span>

<a id="mvc"></a>
### <a name="mvc-template"></a><span data-ttu-id="50896-203">MVC 模板</span><span class="sxs-lookup"><span data-stu-id="50896-203">MVC Template</span></span>

<span data-ttu-id="50896-204">ASP.NET MVC 旨在如促进基于模式的开发实践[测试驱动开发](http://en.wikipedia.org/wiki/Test-driven_development)，[关注点分离](http://en.wikipedia.org/wiki/Separation_of_concerns)，[反向的控件](http://en.wikipedia.org/wiki/Inversion_of_control)，和[依赖关系注入](http://en.wikipedia.org/wiki/Dependency_injection)。</span><span class="sxs-lookup"><span data-stu-id="50896-204">ASP.NET MVC was designed to facilitate patterns-based development practices such as [test-driven development](http://en.wikipedia.org/wiki/Test-driven_development), [separation of concerns](http://en.wikipedia.org/wiki/Separation_of_concerns), [inversion of control](http://en.wikipedia.org/wiki/Inversion_of_control), and [dependency injection](http://en.wikipedia.org/wiki/Dependency_injection).</span></span> <span data-ttu-id="50896-205">框架鼓励将业务逻辑层中其表示层的 web 应用程序分开。</span><span class="sxs-lookup"><span data-stu-id="50896-205">The framework encourages separating the business logic layer of a web application from its presentation layer.</span></span> <span data-ttu-id="50896-206">通过将应用程序划分为模型 (M)、 视图 (V) 和控制器 (C)，ASP.NET MVC 可以更加轻松地管理更大的应用程序中的复杂性。</span><span class="sxs-lookup"><span data-stu-id="50896-206">By dividing the application into models (M), views (V), and controllers (C), ASP.NET MVC can make it easier to manage complexity in larger applications.</span></span>

<span data-ttu-id="50896-207">通过 ASP.NET MVC，您可以更直接与 HTML 和比在 Web 窗体中的 HTTP。</span><span class="sxs-lookup"><span data-stu-id="50896-207">With ASP.NET MVC, you work more directly with HTML and HTTP than in Web Forms.</span></span> <span data-ttu-id="50896-208">例如，Web 窗体可自动保留状态之间的 HTTP 请求，但你必须在 MVC 显式代码。</span><span class="sxs-lookup"><span data-stu-id="50896-208">For example, Web Forms can automatically preserve state between HTTP requests, but you have to code that explicitly in MVC.</span></span> <span data-ttu-id="50896-209">MVC 模型的优点是它，您可以完全控制完全你的应用程序正在执行什么操作和 web 环境中的行为方式。</span><span class="sxs-lookup"><span data-stu-id="50896-209">The advantage of the MVC model is that it enables you to take complete control over exactly what your application is doing and how it behaves in the web environment.</span></span> <span data-ttu-id="50896-210">其缺点在于，你必须编写更多代码。</span><span class="sxs-lookup"><span data-stu-id="50896-210">The disadvantage is that you have to write more code.</span></span>

<span data-ttu-id="50896-211">MVC 的设计目标是可扩展的提供 power 开发人员能够自定义其应用程序需求的框架。</span><span class="sxs-lookup"><span data-stu-id="50896-211">MVC was designed to be extensible, providing power developers the ability to customize the framework for their application needs.</span></span> <span data-ttu-id="50896-212">此外，ASP.NET MVC 源代码，请参阅 OSI 许可证。</span><span class="sxs-lookup"><span data-stu-id="50896-212">In addition, the ASP.NET MVC source code is available under an OSI license.</span></span>

<span data-ttu-id="50896-213">MVC 模板中创建的示例 MVC 5 应用程序使用[Bootstrap](#bootstrap)以提供响应式设计和主题功能。</span><span class="sxs-lookup"><span data-stu-id="50896-213">The MVC template creates a sample MVC 5 application that uses [Bootstrap](#bootstrap) to provide responsive design and theming features.</span></span> <span data-ttu-id="50896-214">下图显示主页页面。</span><span class="sxs-lookup"><span data-stu-id="50896-214">The following illustration shows the home page.</span></span>

![MVC 示例应用程序](creating-web-projects-in-visual-studio/_static/image11.png)

<span data-ttu-id="50896-216">有关 MVC 的详细信息，请参阅[ASP.NET MVC](https://asp.net/mvc)。</span><span class="sxs-lookup"><span data-stu-id="50896-216">For more information about MVC, see [ASP.NET MVC](https://asp.net/mvc).</span></span> <span data-ttu-id="50896-217">有关如何选择 MVC 4 模板的信息，请参阅[Visual Studio 2012 模板](#vs2012)本文后续部分中。</span><span class="sxs-lookup"><span data-stu-id="50896-217">For information about how to select the MVC 4 template, see [Visual Studio 2012 templates](#vs2012) later in this article.</span></span>

<a id="webapi"></a>
### <a name="web-api-template"></a><span data-ttu-id="50896-218">Web API 模板</span><span class="sxs-lookup"><span data-stu-id="50896-218">Web API Template</span></span>

<span data-ttu-id="50896-219">Web API 模板创建基于 Web API，包括 API 帮助页基于 MVC 的示例 web 服务。</span><span class="sxs-lookup"><span data-stu-id="50896-219">The Web API template creates a sample web service based on Web API, including API help pages based on MVC.</span></span>

<span data-ttu-id="50896-220">ASP.NET Web API 是一个框架，可以轻松地生成覆盖广泛的客户端，包括浏览器和移动设备的 HTTP 服务。</span><span class="sxs-lookup"><span data-stu-id="50896-220">ASP.NET Web API is a framework that makes it easy to build HTTP services that reach a broad range of clients, including browsers and mobile devices.</span></span> <span data-ttu-id="50896-221">ASP.NET Web API 是用于在.NET Framework 上生成 RESTful 服务的理想平台。</span><span class="sxs-lookup"><span data-stu-id="50896-221">ASP.NET Web API is an ideal platform for building RESTful services on the .NET Framework.</span></span>

<span data-ttu-id="50896-222">Web API 模板创建的示例 web 服务。</span><span class="sxs-lookup"><span data-stu-id="50896-222">The Web API template creates a sample web service.</span></span> <span data-ttu-id="50896-223">下图显示示例帮助页。</span><span class="sxs-lookup"><span data-stu-id="50896-223">The following illustrations show sample help pages.</span></span>

![Web API 帮助页](creating-web-projects-in-visual-studio/_static/image12.png)

![获取 API 的 web API 帮助页](creating-web-projects-in-visual-studio/_static/image13.png)

<span data-ttu-id="50896-226">有关 Web API 的详细信息，请参阅[ASP.NET Web API](https://asp.net/web-api)。</span><span class="sxs-lookup"><span data-stu-id="50896-226">For more information about Web API, see [ASP.NET Web API](https://asp.net/web-api).</span></span>

<a id="spa"></a>
### <a name="single-page-application-template"></a><span data-ttu-id="50896-227">单页面应用程序模板</span><span class="sxs-lookup"><span data-stu-id="50896-227">Single Page Application Template</span></span>

<span data-ttu-id="50896-228">单页应用程序 (SPA) 模板创建的示例应用程序使用 JavaScript，HTML 5 和[KnockoutJS](http://knockoutjs.com/)上客户端和服务器上的 ASP.NET Web API。</span><span class="sxs-lookup"><span data-stu-id="50896-228">The Single Page Application (SPA) template creates a sample application that uses JavaScript, HTML 5, and [KnockoutJS](http://knockoutjs.com/) on the client, and ASP.NET Web API on the server.</span></span>

<span data-ttu-id="50896-229">SPA 模板的唯一身份验证选项是[单个用户帐户](#indauth)。</span><span class="sxs-lookup"><span data-stu-id="50896-229">The only authentication option for the SPA template is [Individual User Accounts](#indauth).</span></span>

<span data-ttu-id="50896-230">下图显示的示例应用程序的 SPA 模板生成的初始状态。</span><span class="sxs-lookup"><span data-stu-id="50896-230">The following illustration shows the initial state of the sample application that the SPA template builds.</span></span>

![SPA 示例应用程序](creating-web-projects-in-visual-studio/_static/image14.png)

<span data-ttu-id="50896-232">有关如何创建了应用程序使用 SPA 模板的信息，请参阅[Web API 的外部身份验证服务](../../../web-api/overview/security/external-authentication-services.md)。</span><span class="sxs-lookup"><span data-stu-id="50896-232">For information about how to create an application by using the SPA template, see [Web API - External Authentication Services](../../../web-api/overview/security/external-authentication-services.md).</span></span>

<span data-ttu-id="50896-233">有关 ASP.NET 单页面应用程序，以及使用 JavaScript 框架 KnockoutJS 以外的其他 SPA 模板的详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="50896-233">For more information about ASP.NET Single Page Applications, and about additional SPA templates that use JavaScript frameworks other than KnockoutJS, see the following resources:</span></span>

- <span data-ttu-id="50896-234">[ASP.NET 单页面应用程序](../../../single-page-application/index.md)。</span><span class="sxs-lookup"><span data-stu-id="50896-234">[ASP.NET Single Page Application](../../../single-page-application/index.md).</span></span>
- [<span data-ttu-id="50896-235">VS2013 rc 了解 SPA 模板中的安全功能</span><span class="sxs-lookup"><span data-stu-id="50896-235">Understanding Security Features in the SPA Template for VS2013 RC</span></span>](https://blogs.msdn.com/b/webdev/archive/2013/09/20/understanding-security-features-in-spa-template.aspx)
- [<span data-ttu-id="50896-236">单页面应用程序： 生成现代的响应式 Web 应用程序的 ASP.NET</span><span class="sxs-lookup"><span data-stu-id="50896-236">Single-Page Applications: Build Modern, Responsive Web Apps with ASP.NET</span></span>](https://msdn.microsoft.com/en-us/magazine/dn463786.aspx)

<a id="facebook"></a>
### <a name="facebook-template"></a><span data-ttu-id="50896-237">Facebook 模板</span><span class="sxs-lookup"><span data-stu-id="50896-237">Facebook Template</span></span>

<span data-ttu-id="50896-238">你可以安装[Visual Studio 扩展，提供了一个 Facebook 模板](https://go.microsoft.com/fwlink/?LinkID=509965&amp;clcid=0x409)。</span><span class="sxs-lookup"><span data-stu-id="50896-238">You can install a [Visual Studio extension that provides a Facebook template](https://go.microsoft.com/fwlink/?LinkID=509965&amp;clcid=0x409).</span></span> <span data-ttu-id="50896-239">此模板创建的示例应用程序设计为 Facebook 网站中运行。</span><span class="sxs-lookup"><span data-stu-id="50896-239">This template creates a sample application that is designed to run inside the Facebook web site.</span></span> <span data-ttu-id="50896-240">它基于 ASP.NET MVC 并实时更新功能将使用 Web API。</span><span class="sxs-lookup"><span data-stu-id="50896-240">It is based on ASP.NET MVC and uses Web API for real-time update functionality.</span></span>

<span data-ttu-id="50896-241">任何身份验证选项不是适用于 Facebook 模板，因为 Facebook 应用程序的 Facebook 站点内运行，并依赖于 Facebook 的身份验证。</span><span class="sxs-lookup"><span data-stu-id="50896-241">No authentication options are available for the Facebook template because Facebook applications run within the Facebook site and rely on Facebook's authentication.</span></span>

<span data-ttu-id="50896-242">有关 ASP.NET Facebook 应用程序的详细信息，请参阅[更新 MVC Facebook API](https://blogs.msdn.com/b/webdev/archive/2014/06/10/updating-the-mvc-facebook-api.aspx)。</span><span class="sxs-lookup"><span data-stu-id="50896-242">For more information about ASP.NET Facebook applications, see [Updating the MVC Facebook API](https://blogs.msdn.com/b/webdev/archive/2014/06/10/updating-the-mvc-facebook-api.aspx).</span></span>

<a id="vs2012"></a>
### <a name="visual-studio-2012-templates"></a><span data-ttu-id="50896-243">Visual Studio 2012 模板</span><span class="sxs-lookup"><span data-stu-id="50896-243">Visual Studio 2012 Templates</span></span>

<span data-ttu-id="50896-244">Visual Studio 2013 web 项目创建对话框不提供对在 Visual Studio 2012 中提供的一些模板的访问。</span><span class="sxs-lookup"><span data-stu-id="50896-244">The Visual Studio 2013 web project creation dialog does not provide access to some templates that were available in Visual Studio 2012.</span></span> <span data-ttu-id="50896-245">如果你想要使用这些模板之一，你可以单击 Visual Studio 的新项目对话框的左窗格中的 Visual Studio 2012 节点。</span><span class="sxs-lookup"><span data-stu-id="50896-245">If you want to use one of these templates, you can click the Visual Studio 2012 node in the left pane of the Visual Studio New Project dialog box.</span></span>

![Visual Studio 2012 模板](creating-web-projects-in-visual-studio/_static/image15.png)

<span data-ttu-id="50896-247">**Visual Studio 2012**节点允许您选择不具有以下 web 模板将在模板的默认列表的访问 Visual Studio 2013:</span><span class="sxs-lookup"><span data-stu-id="50896-247">The **Visual Studio 2012** node lets you choose the following web templates that you don't have access to in the default list of templates for Visual Studio 2013:</span></span>

- <span data-ttu-id="50896-248">ASP.NET MVC 4 Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="50896-248">ASP.NET MVC 4 Web Application</span></span>
- <span data-ttu-id="50896-249">ASP.NET 动态数据实体 Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="50896-249">ASP.NET Dynamic Data Entities Web Application</span></span>
- <span data-ttu-id="50896-250">ASP.NET AJAX 服务器控件</span><span class="sxs-lookup"><span data-stu-id="50896-250">ASP.NET AJAX Server Control</span></span>
- <span data-ttu-id="50896-251">ASP.NET AJAX 服务器控件扩展程序</span><span class="sxs-lookup"><span data-stu-id="50896-251">ASP.NET AJAX Server Control Extender</span></span>
- <span data-ttu-id="50896-252">ASP.NET 服务器控件</span><span class="sxs-lookup"><span data-stu-id="50896-252">ASP.NET Server Control</span></span>

<a id="bootstrap"></a>
## <a name="bootstrap-in-the-visual-studio-2013-web-project-templates"></a><span data-ttu-id="50896-253">启动 Visual Studio 2013 web 项目模板中</span><span class="sxs-lookup"><span data-stu-id="50896-253">Bootstrap in the Visual Studio 2013 web project templates</span></span>

<span data-ttu-id="50896-254">Visual Studio 2013 项目模板使用[Bootstrap](http://getbootstrap.com/)，由 Twitter 的布局和主题框架。</span><span class="sxs-lookup"><span data-stu-id="50896-254">The Visual Studio 2013 project templates use [Bootstrap](http://getbootstrap.com/), a layout and theming framework created by Twitter.</span></span> <span data-ttu-id="50896-255">Bootstrap 使用 CSS3 提供响应灵敏的设计，这意味着布局可以动态调整以适应不同的浏览器窗口大小。</span><span class="sxs-lookup"><span data-stu-id="50896-255">Bootstrap uses CSS3 to provide responsive design, which means layouts can dynamically adapt to different browser window sizes.</span></span> <span data-ttu-id="50896-256">例如，在宽的浏览器窗口中创建 Web 窗体模板的主页上类似于下图：</span><span class="sxs-lookup"><span data-stu-id="50896-256">For example, in a wide browser window the home page created by the Web Forms template looks like the following illustration:</span></span>

![Web 窗体模板的应用程序主页](creating-web-projects-in-visual-studio/_static/image16.png)

<span data-ttu-id="50896-258">使窗口变窄，请和水平排列的列将移动到垂直排列：</span><span class="sxs-lookup"><span data-stu-id="50896-258">Make the window narrower, and the horizontally arranged columns move into vertical arrangement:</span></span>

![启动垂直列排列方式](creating-web-projects-in-visual-studio/_static/image17.png)

<span data-ttu-id="50896-260">有点令缩小窗口并水平顶部的菜单将转变为可单击以展开到垂直方向菜单的图标：</span><span class="sxs-lookup"><span data-stu-id="50896-260">Narrow the window a little more, and the horizontal top menu turns into an icon that you can click to expand into a vertically oriented menu:</span></span>

![启动菜单图标](creating-web-projects-in-visual-studio/_static/image18.png)

![启动垂直菜单](creating-web-projects-in-visual-studio/_static/image19.png)

<span data-ttu-id="50896-263">Bootstrap 的主题功能还可用于轻松地影响应用程序的外观和行为的更改。</span><span class="sxs-lookup"><span data-stu-id="50896-263">You can also use Bootstrap's theming feature to easily effect a change in the application's look and feel.</span></span> <span data-ttu-id="50896-264">例如，你可以执行以下步骤以更改的主题。</span><span class="sxs-lookup"><span data-stu-id="50896-264">For example, you can do the following steps to change the theme.</span></span>

1. <span data-ttu-id="50896-265">在浏览器中，转到[http://Bootswatch.com](http://Bootswatch.com)，选择一个主题，然后单击**下载**。</span><span class="sxs-lookup"><span data-stu-id="50896-265">In your browser, go to [http://Bootswatch.com](http://Bootswatch.com), choose a theme, and then click **Download**.</span></span> <span data-ttu-id="50896-266">(这会将下载*bootstrap.min.css*默认情况下; 如果你想要检查 CSS 代码，获取*bootstrap.css*而不是缩减的版本。)</span><span class="sxs-lookup"><span data-stu-id="50896-266">(This downloads *bootstrap.min.css* by default; if you want to examine the CSS code, get *bootstrap.css* instead of the minified version.)</span></span>
2. <span data-ttu-id="50896-267">下载的 CSS 文件的内容复制。</span><span class="sxs-lookup"><span data-stu-id="50896-267">Copy the contents of the downloaded CSS file.</span></span>
3. <span data-ttu-id="50896-268">在 Visual Studio 中，创建一个新**样式表**名为文件*bootstrap theme.css*中*内容*文件夹，然后粘贴下载 CSS 代码到它。</span><span class="sxs-lookup"><span data-stu-id="50896-268">In Visual Studio, create a new **Style Sheet** file named *bootstrap-theme.css* in the *Content* folder and paste the downloaded CSS code into it.</span></span>
4. <span data-ttu-id="50896-269">打开*应用\_Start/Bundle.config*和更改*bootstrap.css*到*bootstrap theme.css*。</span><span class="sxs-lookup"><span data-stu-id="50896-269">Open *App\_Start/Bundle.config* and change *bootstrap.css* to *bootstrap-theme.css*.</span></span>

<span data-ttu-id="50896-270">再次运行该项目，并且该应用程序的新面貌。</span><span class="sxs-lookup"><span data-stu-id="50896-270">Run the project again, and the application has a new look.</span></span> <span data-ttu-id="50896-271">下图显示 Amelia 主题的效果：</span><span class="sxs-lookup"><span data-stu-id="50896-271">The following illustration shows the effect of the Amelia theme:</span></span>

![Bootstrap Amelia 主题](creating-web-projects-in-visual-studio/_static/image20.png)

<span data-ttu-id="50896-273">许多 Bootstrap 主题有免费和高级版的版本。</span><span class="sxs-lookup"><span data-stu-id="50896-273">Many Bootstrap themes are available, both free and premium versions.</span></span> <span data-ttu-id="50896-274">Bootstrap 还提供了各种用户界面组件，如[下拉列表](http://twitter.github.io/bootstrap/components.html#dropdowns)，[按钮组](http://twitter.github.io/bootstrap/components.html#buttonGroups)，和[图标](http://twitter.github.io/bootstrap/base-css.html#images)。</span><span class="sxs-lookup"><span data-stu-id="50896-274">Bootstrap also offers a wide variety of UI components, such as [drop-downs](http://twitter.github.io/bootstrap/components.html#dropdowns), [button groups](http://twitter.github.io/bootstrap/components.html#buttonGroups), and [icons](http://twitter.github.io/bootstrap/base-css.html#images).</span></span> <span data-ttu-id="50896-275">有关 Bootstrap 的详细信息，请参阅[启动站点](http://twitter.github.io/bootstrap/)。</span><span class="sxs-lookup"><span data-stu-id="50896-275">For more information about Bootstrap, see [the Bootstrap site](http://twitter.github.io/bootstrap/).</span></span>

<span data-ttu-id="50896-276">如果在 Visual Studio 中使用 Web 窗体设计器，请注意设计器不支持 CSS3，因此它准确地反映的 Bootstrap 主题或响应式布局更改的所有结果。</span><span class="sxs-lookup"><span data-stu-id="50896-276">If you use the Web Forms designer in Visual Studio, note that the designer doesn't support CSS3, so it doesn't accurately show all the effects of Bootstrap themes or responsive layout changes.</span></span> <span data-ttu-id="50896-277">但是，Web 窗体页面将显示正确使用的浏览器查看时。</span><span class="sxs-lookup"><span data-stu-id="50896-277">However, the Web Forms pages will display correctly when viewed with a browser.</span></span>

<a id="add"></a>
## <a name="adding-support-for-additional-frameworks"></a><span data-ttu-id="50896-278">添加对其他框架的支持</span><span class="sxs-lookup"><span data-stu-id="50896-278">Adding Support for Additional Frameworks</span></span>

<span data-ttu-id="50896-279">当你选择的模板时，自动选择模板使用 framework(s) 复选框。</span><span class="sxs-lookup"><span data-stu-id="50896-279">When you select a template, the check box for the framework(s) used by the template is automatically selected.</span></span> <span data-ttu-id="50896-280">例如，如果你选择**Web 窗体**模板， **Web 窗体**复选框处于选中状态，无法将其清除。</span><span class="sxs-lookup"><span data-stu-id="50896-280">For example, if you select the **Web Forms** template, the **Web Forms** check box is selected and you can't clear it.</span></span>

![选择模板](creating-web-projects-in-visual-studio/_static/image21.png)

![添加框架](creating-web-projects-in-visual-studio/_static/image22.png)

<span data-ttu-id="50896-283">你可以选择不包括在模板以创建项目时添加对该 framework 的支持的框架复选框。</span><span class="sxs-lookup"><span data-stu-id="50896-283">You can select the check box for a framework that isn't included in the template in order to add support for that framework when the project is created.</span></span> <span data-ttu-id="50896-284">例如，若要启用的 Web 窗体使用*.aspx*页，如果你已选择 MVC 模板中，选择**Web 窗体**复选框。</span><span class="sxs-lookup"><span data-stu-id="50896-284">For example, to enable the use of Web Forms *.aspx* pages when you've selected the MVC template, select the **Web Forms** check box.</span></span> <span data-ttu-id="50896-285">若要在你使用 Web 窗体模板时，请启用 MVC，单击或**MVC**复选框。</span><span class="sxs-lookup"><span data-stu-id="50896-285">Or to enable MVC when you're using the Web Forms template, click the **MVC** check box.</span></span> <span data-ttu-id="50896-286">添加一个框架，使设计时，以及运行时支持。</span><span class="sxs-lookup"><span data-stu-id="50896-286">Adding a framework enables design-time as well as run-time support.</span></span> <span data-ttu-id="50896-287">例如，如果 MVC 支持添加到 Web 窗体项目时，你将能够创建控制器和视图的基架。</span><span class="sxs-lookup"><span data-stu-id="50896-287">For example, if you add MVC support to a Web Forms project, you will be able to scaffold controllers and views.</span></span>

<span data-ttu-id="50896-288">如果你将 Web 窗体和 MVC 合并项目中，启用[友好 Url](http://www.hanselman.com/blog/IntroducingASPNETFriendlyUrlsCleanerURLsEasierRoutingAndMobileViewsForASPNETWebForms.aspx)在 Web 窗体，可能会有意外路由问题有一个 URL，其中具有多个可能的目标。</span><span class="sxs-lookup"><span data-stu-id="50896-288">If you combine Web Forms and MVC in a project and enable [Friendly URLs](http://www.hanselman.com/blog/IntroducingASPNETFriendlyUrlsCleanerURLsEasierRoutingAndMobileViewsForASPNETWebForms.aspx) in Web Forms, there might be unexpected routing problems where one URL has multiple possible targets.</span></span> <span data-ttu-id="50896-289">定义的路由首先将优先。</span><span class="sxs-lookup"><span data-stu-id="50896-289">The routes that are defined first will take precedence.</span></span> <span data-ttu-id="50896-290">例如，如果你有`Home`控制器和一个*Home.aspx*页上， `http://contoso.com/home` URL 将转到*Home.aspx*如果调用`EnableFriendlyUrls`方法之前调用`MapRoute`中的方法*RouteConfig.cs*，或者相同的 URL 将转到的默认视图你`Home`控制器如果调用`MapRoute`之前`EnableFriendlyUrls`。</span><span class="sxs-lookup"><span data-stu-id="50896-290">For example, if you have a `Home` controller and a *Home.aspx* page, the `http://contoso.com/home` URL will go to *Home.aspx* if you call the `EnableFriendlyUrls` method before you call the `MapRoute` method in *RouteConfig.cs*, or the same URL will go to the default view for your `Home` controller if you call `MapRoute` before `EnableFriendlyUrls`.</span></span>

<span data-ttu-id="50896-291">添加一个框架，不会添加任何示例应用程序功能。</span><span class="sxs-lookup"><span data-stu-id="50896-291">Adding a framework does not add any sample application functionality.</span></span> <span data-ttu-id="50896-292">例如，如果你添加 Web 窗体支持如果你已选择 MVC 模板中，不*Default.aspx*创建主页文件。</span><span class="sxs-lookup"><span data-stu-id="50896-292">For example, if you add Web Forms support when you've selected the MVC template, no *Default.aspx* home page file is created.</span></span> <span data-ttu-id="50896-293">添加文件夹、 文件和支持 framework 所需的引用。</span><span class="sxs-lookup"><span data-stu-id="50896-293">Only the folders, files, and references required to support the framework are added.</span></span> <span data-ttu-id="50896-294">因此，添加框架不会更改由通过模板创建的示例应用程序中的代码实现的身份验证选项。</span><span class="sxs-lookup"><span data-stu-id="50896-294">For that reason, adding frameworks doesn't change authentication options, which are implemented by code in sample applications created by the templates.</span></span> <span data-ttu-id="50896-295">例如，如果你选择空模板并添加 Web 窗体或 MVC 支持，**配置身份验证**仍为已禁用按钮。</span><span class="sxs-lookup"><span data-stu-id="50896-295">For example, if you select the Empty template and add Web Forms or MVC support, the **Configure Authentication** button will still be disabled.</span></span>

<span data-ttu-id="50896-296">下列各节简要描述每个复选框的效果。</span><span class="sxs-lookup"><span data-stu-id="50896-296">The following sections describe briefly the effect of each check box.</span></span>

### <a name="add-web-forms-support"></a><span data-ttu-id="50896-297">添加 Web 窗体支持</span><span class="sxs-lookup"><span data-stu-id="50896-297">Add Web Forms Support</span></span>

<span data-ttu-id="50896-298">创建空*应用\_数据*和*模型*文件夹和*Global.asax*文件。</span><span class="sxs-lookup"><span data-stu-id="50896-298">Creates empty *App\_Data* and *Models* folders and a *Global.asax* file.</span></span> <span data-ttu-id="50896-299">这些已创建的所有模板而不是空的模板，因此选择 Web 窗体复选框没有任何区别其他模板。</span><span class="sxs-lookup"><span data-stu-id="50896-299">These are already created by all templates other than the Empty template, so selecting the Web Forms check box makes no difference for other templates.</span></span>

<span data-ttu-id="50896-300">默认情况下，但当你添加到其他模板支持通过选择友好的 Url 不会自动启用 Web 窗体复选框的 Web 窗体时，Web 窗体模板使友好的 Url。</span><span class="sxs-lookup"><span data-stu-id="50896-300">The Web Forms template enables Friendly URLs by default, but when you add Web Forms support to other templates by selecting the Web Forms check box Friendly URLs are not automatically enabled.</span></span>

### <a name="add-mvc-support"></a><span data-ttu-id="50896-301">添加的 MVC 支持</span><span class="sxs-lookup"><span data-stu-id="50896-301">Add MVC Support</span></span>

<span data-ttu-id="50896-302">安装 MVC、 Razor 和网页 NuGet 包，创建空*应用\_数据*，*控制器*，*模型*，和*视图*文件夹，创建*应用\_启动*文件夹*RouteConfig.cs*文件中，并创建*Global.asax*文件。</span><span class="sxs-lookup"><span data-stu-id="50896-302">Installs MVC, Razor, and WebPages NuGet packages, creates empty *App\_Data*, *Controllers*, *Models*, and *Views* folders, creates *App\_Start* folder with *RouteConfig.cs* file, and creates *Global.asax* file.</span></span>

### <a name="add-web-api-support"></a><span data-ttu-id="50896-303">添加 Web API 支持</span><span class="sxs-lookup"><span data-stu-id="50896-303">Add Web API Support</span></span>

<span data-ttu-id="50896-304">安装 WebApi 和 Newtonsoft.Json NuGet 包，创建空*应用\_数据*，*控制器*，和*模型*文件夹，创建*应用\_启动*文件夹*WebApiConfig.cs*文件中，并创建*Global.asax*文件。</span><span class="sxs-lookup"><span data-stu-id="50896-304">Installs WebApi and Newtonsoft.Json NuGet packages, creates empty *App\_Data*, *Controllers*, and *Models* folders, creates *App\_Start* folder with *WebApiConfig.cs* file, and creates *Global.asax* file.</span></span>

<a id="auth"></a>
## <a name="authentication-methods"></a><span data-ttu-id="50896-305">身份验证方法</span><span class="sxs-lookup"><span data-stu-id="50896-305">Authentication Methods</span></span>

<span data-ttu-id="50896-306">Visual Studio 2013 提供 Web 窗体、 MVC 和 Web API 模板的多个身份验证选项：</span><span class="sxs-lookup"><span data-stu-id="50896-306">Visual Studio 2013 offers several authentication options for the Web Forms, MVC, and Web API templates:</span></span>

- [<span data-ttu-id="50896-307">无身份验证</span><span class="sxs-lookup"><span data-stu-id="50896-307">No Authentication</span></span>](#noauth)
- <span data-ttu-id="50896-308">[单个用户帐户](#indauth)（ASP.NET 标识，以前称为 ASP.NET 成员资格）</span><span class="sxs-lookup"><span data-stu-id="50896-308">[Individual User Accounts](#indauth) (ASP.NET Identity, formerly known as ASP.NET membership)</span></span>
- <span data-ttu-id="50896-309">[组织帐户](#orgauth)（Windows Server Active Directory 或 Azure Active Directory）</span><span class="sxs-lookup"><span data-stu-id="50896-309">[Organizational Accounts](#orgauth) (Windows Server Active Directory or Azure Active Directory)</span></span>
- <span data-ttu-id="50896-310">[Windows 身份验证](#winauth)(Intranet)</span><span class="sxs-lookup"><span data-stu-id="50896-310">[Windows Authentication](#winauth) (Intranet)</span></span>

![配置身份验证对话框](creating-web-projects-in-visual-studio/_static/image23.png)

<a id="noauth"></a>

### <a name="no-authentication"></a><span data-ttu-id="50896-312">无身份验证</span><span class="sxs-lookup"><span data-stu-id="50896-312">No Authentication</span></span>

<span data-ttu-id="50896-313">如果你选择**无身份验证**、 示例应用程序将包含用于登录的任何网页、 不 UI 中，该值指示登录的用户，没有实体类的成员资格数据库和的成员资格数据库没有连接字符串。</span><span class="sxs-lookup"><span data-stu-id="50896-313">If you select **No Authentication**, the sample application will contain no web pages for logging in, no UI indicating who is logged in, no entity classes for a membership database, and no connection string for a membership database.</span></span>

<a id="indauth"></a>
### <a name="individual-user-accounts"></a><span data-ttu-id="50896-314">单个用户帐户</span><span class="sxs-lookup"><span data-stu-id="50896-314">Individual User Accounts</span></span>

<span data-ttu-id="50896-315">如果你选择**单个用户帐户**，示例应用程序将配置为使用 ASP.NET 标识 （以前称为 ASP.NET 成员资格） 进行用户身份验证。</span><span class="sxs-lookup"><span data-stu-id="50896-315">If you select **Individual User Accounts**, the sample application will be configured to use ASP.NET Identity (formerly known as ASP.NET membership) for user authentication.</span></span> <span data-ttu-id="50896-316">ASP.NET 标识使用户可以注册一个帐户，通过在站点上创建用户名和密码或使用社交提供程序，如 Facebook、 Google、 Microsoft 帐户或 Twitter 登录。</span><span class="sxs-lookup"><span data-stu-id="50896-316">ASP.NET Identity enables a user to register an account, by creating a username and password on the site or by signing in with social providers such as Facebook, Google, Microsoft Account, or Twitter.</span></span> <span data-ttu-id="50896-317">在 ASP.NET Identity 中的用户配置文件的默认数据存储是一个 SQL Server LocalDB 数据库，它可以在生产站点对 SQL Server 或 Azure SQL 数据库部署。</span><span class="sxs-lookup"><span data-stu-id="50896-317">The default data store for user profiles in ASP.NET Identity is a SQL Server LocalDB database, which you can deploy to SQL Server or Azure SQL Database for the production site.</span></span>

<span data-ttu-id="50896-318">在 Visual Studio 2013 中这些功能与 Visual Studio 2012 中的相同，但已重新编写 ASP.NET 成员资格系统的基础代码。</span><span class="sxs-lookup"><span data-stu-id="50896-318">In Visual Studio 2013 these features are the same as in Visual Studio 2012, but the underlying code for the ASP.NET membership system has been rewritten.</span></span> <span data-ttu-id="50896-319">新的基本代码的优点包括：</span><span class="sxs-lookup"><span data-stu-id="50896-319">Advantages of the new code base include the following:</span></span>

- <span data-ttu-id="50896-320">新的成员资格系统基于[OWIN](http://owin.org/)而不是 ASP.NET 窗体身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="50896-320">The new membership system is based on [OWIN](http://owin.org/) rather than the ASP.NET Forms Authentication module.</span></span> <span data-ttu-id="50896-321">这意味着，你可以使用相同的身份验证机制，是否在你在 IIS 中，使用 Web 窗体或 MVC 或你在自承载 Web API 或 SignalR。</span><span class="sxs-lookup"><span data-stu-id="50896-321">This means that you can use the same authentication mechanism whether you're using Web Forms or MVC in IIS, or you're self-hosting Web API or SignalR.</span></span>
- <span data-ttu-id="50896-322">新的成员资格数据库由 Entity Framework Code First，和由你可以修改的实体类表示的所有表。</span><span class="sxs-lookup"><span data-stu-id="50896-322">The new membership database is managed by Entity Framework Code First, and all of the tables are represented by entity classes that you can modify.</span></span> <span data-ttu-id="50896-323">这意味着可以轻松自定义的数据库架构和配置文件相关的 web UI，以满足你自己的需求，并且你可以轻松部署使用 Code First 迁移更新。</span><span class="sxs-lookup"><span data-stu-id="50896-323">This means that you can easily customize the database schema and profile-related web UI to fit your own needs, and you can easily deploy your updates using Code First Migrations.</span></span>

<span data-ttu-id="50896-324">在新的模板中，自动实现新的成员身份系统，并且它可以是实现在面向.NET 4.5 的任何项目中手动或更高版本。</span><span class="sxs-lookup"><span data-stu-id="50896-324">The new membership system is implemented automatically in the new templates, and it can be implemented manually in any project that targets .NET 4.5 or later.</span></span>

<span data-ttu-id="50896-325">如果你要创建 Internet 网站，这是主要用于外部客户，ASP.NET 标识是一个不错的选择。</span><span class="sxs-lookup"><span data-stu-id="50896-325">ASP.NET Identity is a good choice if you are creating an Internet web site which is mainly for external customers.</span></span> <span data-ttu-id="50896-326">如果你的组织使用 Active Directory 或 Office 365 和你想要创建的项目是启用单一登录为员工和业务合作伙伴**组织帐户**选项可能是更好的选择。</span><span class="sxs-lookup"><span data-stu-id="50896-326">If your organization uses Active Directory or Office 365 and you want to create a project that enables single-sign-on for employees and business partners, the **Organizational Accounts** option might be a better choice.</span></span>

<span data-ttu-id="50896-327">有关单个用户帐户选项的详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="50896-327">For more information about the Individual User Accounts option, see the following resources:</span></span>

- <span data-ttu-id="50896-328">[www.asp.net/identity](../../../identity/index.md)。</span><span class="sxs-lookup"><span data-stu-id="50896-328">[www.asp.net/identity](../../../identity/index.md).</span></span> <span data-ttu-id="50896-329">有关 ASP.NET Identity ASP.NET web 站点上的文档。</span><span class="sxs-lookup"><span data-stu-id="50896-329">Documentation about ASP.NET Identity on the ASP.NET web site.</span></span>
- <span data-ttu-id="50896-330">[创建 ASP.NET MVC 5 应用程序使用 Facebook 和 Google OAuth2 和 OpenID 登录](../../../mvc/overview/security/create-an-aspnet-mvc-5-app-with-facebook-and-google-oauth2-and-openid-sign-on.md)。</span><span class="sxs-lookup"><span data-stu-id="50896-330">[Create an ASP.NET MVC 5 App with Facebook and Google OAuth2 and OpenID Sign-on](../../../mvc/overview/security/create-an-aspnet-mvc-5-app-with-facebook-and-google-oauth2-and-openid-sign-on.md).</span></span> <span data-ttu-id="50896-331">此外演示如何自定义用户配置文件数据。</span><span class="sxs-lookup"><span data-stu-id="50896-331">Also shows how to customize user profile data.</span></span>
- [<span data-ttu-id="50896-332">Web API 的外部身份验证服务</span><span class="sxs-lookup"><span data-stu-id="50896-332">Web API - External Authentication Services</span></span>](../../../web-api/overview/security/external-authentication-services.md)
- [<span data-ttu-id="50896-333">将外部登录名添加到你在 Visual Studio 2013 的 ASP.NET 应用程序</span><span class="sxs-lookup"><span data-stu-id="50896-333">Adding External Logins to your ASP.NET application in Visual Studio 2013</span></span>](https://blogs.msdn.com/b/webdev/archive/2013/06/27/adding-external-logins-to-your-asp-net-application-in-visual-studio-2013.aspx)

<a id="orgauth"></a>
### <a name="organizational-accounts"></a><span data-ttu-id="50896-334">组织帐户</span><span class="sxs-lookup"><span data-stu-id="50896-334">Organizational Accounts</span></span>

<span data-ttu-id="50896-335">如果你选择**组织帐户**，示例应用程序将配置为使用 Windows Identity Foundation (WIF) 进行基于 Azure Active Directory (Azure AD，其中包括 Office 365) 中的用户帐户的身份验证或Windows Server Active Directory。</span><span class="sxs-lookup"><span data-stu-id="50896-335">If you select **Organizational Accounts**, the sample application will be configured to use Windows Identity Foundation (WIF) for authentication based on user accounts in Azure Active Directory (Azure AD, which includes Office 365) or Windows Server Active Directory.</span></span> <span data-ttu-id="50896-336">有关详细信息，请参阅[组织帐户身份验证选项](#orgauthoptions)本主题中更高版本。</span><span class="sxs-lookup"><span data-stu-id="50896-336">For more information, see [Organizational account authentication options](#orgauthoptions) later in this topic.</span></span>

<a id="winauth"></a>
### <a name="windows-authentication"></a><span data-ttu-id="50896-337">Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="50896-337">Windows Authentication</span></span>

<span data-ttu-id="50896-338">如果你选择**Windows 身份验证**，示例应用程序将配置为使用 Windows 身份验证 IIS 模块进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="50896-338">If you select **Windows Authentication**, the sample application will be configured to use the Windows Authentication IIS module for authentication.</span></span> <span data-ttu-id="50896-339">应用程序将显示 Active directory 或本地计算机帐户的登录到 Windows，但不会包括用户注册或登录 UI 的域和用户 ID。</span><span class="sxs-lookup"><span data-stu-id="50896-339">The application will display the domain and user ID of the Active directory or local machine account that is logged into Windows but won't include user registration or log-in UI.</span></span> <span data-ttu-id="50896-340">此选项适用于 Intranet 网站。</span><span class="sxs-lookup"><span data-stu-id="50896-340">This option is intended for Intranet web sites.</span></span>

<span data-ttu-id="50896-341">或者，可以创建 Intranet 站点使用 AD 身份验证通过选择[本地组织的帐户下的选项](#orgauthonprem)。</span><span class="sxs-lookup"><span data-stu-id="50896-341">Alternatively, you can create an Intranet site that uses AD authentication by choosing the [On-Premises option under Organizational Accounts](#orgauthonprem).</span></span> <span data-ttu-id="50896-342">本地选项使用 Windows Identity Foundation (WIF)，而不是 Windows 身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="50896-342">The On-Premises option uses Windows Identity Foundation (WIF) instead of the Windows Authentication module.</span></span> <span data-ttu-id="50896-343">若要设置的本地选项中，需要执行一些其他步骤，但 WIF 使不可适用于 Windows 身份验证模块的功能。</span><span class="sxs-lookup"><span data-stu-id="50896-343">Some additional steps are required in order to set up the On-Premises option, but WIF enables features that aren't available with the Windows Authentication module.</span></span> <span data-ttu-id="50896-344">例如，与 WIF 可以配置应用程序访问在 Active Directory 和查询目录数据。</span><span class="sxs-lookup"><span data-stu-id="50896-344">For example, with WIF you can configure application access in Active Directory and query directory data.</span></span>

<a id="orgauthoptions"></a>
## <a name="organizational-account-authentication-options"></a><span data-ttu-id="50896-345">组织帐户身份验证选项</span><span class="sxs-lookup"><span data-stu-id="50896-345">Organizational account authentication options</span></span>

<span data-ttu-id="50896-346">**配置身份验证**对话框为你提供了 Azure Active Directory (Azure AD，其中包括 Office 365) 或 Windows Server Active Directory (AD) 帐户身份验证的几个选项：</span><span class="sxs-lookup"><span data-stu-id="50896-346">The **Configure Authentication** dialog gives you several options for Azure Active Directory (Azure AD, which includes Office 365) or Windows Server Active Directory (AD) account authentication:</span></span>

- <span data-ttu-id="50896-347">[云-单个组织](#orgauthsingle)(Azure AD 或使用与 Azure AD 目录集成的 AD)</span><span class="sxs-lookup"><span data-stu-id="50896-347">[Cloud - Single Organization](#orgauthsingle) (Azure AD, or AD using directory integration with Azure AD)</span></span>
- <span data-ttu-id="50896-348">[云-多组织](#orgauthmulti)(Azure AD 或使用与 Azure AD 目录集成的 AD)</span><span class="sxs-lookup"><span data-stu-id="50896-348">[Cloud - Multi Organization](#orgauthmulti) (Azure AD, or AD using directory integration with Azure AD)</span></span>
- <span data-ttu-id="50896-349">[在本地](#orgauthonprem)(AD)</span><span class="sxs-lookup"><span data-stu-id="50896-349">[On-Premises](#orgauthonprem) (AD)</span></span>

<span data-ttu-id="50896-350">如果你想要尝试 Azure AD 选项之一，但还没有帐户，[单击此处注册 Azure AD 帐户](https://go.microsoft.com/fwlink/?LinkId=309942)。</span><span class="sxs-lookup"><span data-stu-id="50896-350">If you want to try one of the Azure AD options but don't have an account yet, [click here to sign up for a Azure AD account](https://go.microsoft.com/fwlink/?LinkId=309942).</span></span>

> [!NOTE]
> <span data-ttu-id="50896-351">如果你选择的 Azure AD 选项之一，你的项目需要一个数据库，您必须为你的 Azure AD 租户全局管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="50896-351">If you choose one of the Azure AD options, your project requires a database and you have to sign in to a global administrator account for your Azure AD tenant.</span></span> <span data-ttu-id="50896-352">输入组织帐户的名称和密码 (例如， admin@contoso.onmicrosoft.com)，其对你的 Azure AD 租户的管理权限。</span><span class="sxs-lookup"><span data-stu-id="50896-352">Enter the name and password for an organizational account (for example, admin@contoso.onmicrosoft.com) that has administrative permissions for your Azure AD tenant.</span></span>
> 
> <span data-ttu-id="50896-353">**不要输入 Microsoft 帐户的凭据 (例如， contoso@hotmail.com) 在登录对话框中。**</span><span class="sxs-lookup"><span data-stu-id="50896-353">**Don't enter credentials for a Microsoft account (for example, contoso@hotmail.com) in the sign-in dialog box.**</span></span>


<a id="orgauthsingle"></a>
### <a name="cloud---single-organization-authentication"></a><span data-ttu-id="50896-354">云-单个组织身份验证</span><span class="sxs-lookup"><span data-stu-id="50896-354">Cloud - Single Organization Authentication</span></span>

![单个组织身份验证](creating-web-projects-in-visual-studio/_static/image24.png)

<span data-ttu-id="50896-356">如果你想要启用的用户帐户的一个 Azure AD 中定义的身份验证，请选择此选项[租户](https://technet.microsoft.com/en-us/library/jj573650.aspx)。</span><span class="sxs-lookup"><span data-stu-id="50896-356">Choose this option if you want to enable authentication for user accounts that are defined in one Azure AD [tenant](https://technet.microsoft.com/en-us/library/jj573650.aspx).</span></span> <span data-ttu-id="50896-357">例如，该网站为 contoso.com，而且它将可供 contoso.onmicrosoft.com 租户中的 Contoso 公司员工。</span><span class="sxs-lookup"><span data-stu-id="50896-357">For example, the site is contoso.com and it will be made available to employees of the Contoso Company who are in the contoso.onmicrosoft.com tenant.</span></span> <span data-ttu-id="50896-358">你将无法配置 Azure AD，以允许用户从其他租户可以访问应用程序。</span><span class="sxs-lookup"><span data-stu-id="50896-358">You won't be able to configure Azure AD to allow users from other tenants to access the application.</span></span>

#### <a name="domain"></a><span data-ttu-id="50896-359">Domain</span><span class="sxs-lookup"><span data-stu-id="50896-359">Domain</span></span>

<span data-ttu-id="50896-360">输入你想要在设置应用程序，例如 Azure AD 域： `contoso.onmicrosoft.com`。</span><span class="sxs-lookup"><span data-stu-id="50896-360">Enter the Azure AD domain that you want to set up the application in, for example: `contoso.onmicrosoft.com`.</span></span> <span data-ttu-id="50896-361">如果你有[自定义域](http://www.cloudidentity.com/blog/2013/04/14/adding-a-custom-domain-to-your-windows-azure-ad/)，如`contoso.com`而不是`contoso.onmicrosoft.com`，你可以在此处输入的。</span><span class="sxs-lookup"><span data-stu-id="50896-361">If you have a [custom domain](http://www.cloudidentity.com/blog/2013/04/14/adding-a-custom-domain-to-your-windows-azure-ad/), such as `contoso.com` instead of `contoso.onmicrosoft.com`, you can enter that here.</span></span>

#### <a name="access-level"></a><span data-ttu-id="50896-362">访问级别</span><span class="sxs-lookup"><span data-stu-id="50896-362">Access Level</span></span>

<span data-ttu-id="50896-363">如果应用程序需要查询或通过使用 Graph API 更新目录信息，请选择**上单一登录、 读取目录数据**或**上单一登录，读取和写入目录数据**。</span><span class="sxs-lookup"><span data-stu-id="50896-363">If the application needs to query or update directory information by using the Graph API, choose **Single Sign-On, Read Directory Data** or **Single Sign-On, Read and Write Directory Data**.</span></span> <span data-ttu-id="50896-364">否则，请选择**上单一登录**。</span><span class="sxs-lookup"><span data-stu-id="50896-364">Otherwise, choose **Single Sign-On**.</span></span> <span data-ttu-id="50896-365">有关详细信息，请参阅[应用程序访问级别](https://msdn.microsoft.com/en-us/library/windowsazure/b08d91fa-6a64-4deb-92f4-f5857add9ed8#BKMK_AccessLevels)和[使用 Graph API 查询 Azure AD](https://msdn.microsoft.com/en-US/library/windowsazure/dn151791.aspx)。</span><span class="sxs-lookup"><span data-stu-id="50896-365">For more information, see [Application Access Levels](https://msdn.microsoft.com/en-us/library/windowsazure/b08d91fa-6a64-4deb-92f4-f5857add9ed8#BKMK_AccessLevels) and [Using the Graph API to Query Azure AD](https://msdn.microsoft.com/en-US/library/windowsazure/dn151791.aspx).</span></span>

#### <a name="application-id-uri"></a><span data-ttu-id="50896-366">应用程序 ID URI</span><span class="sxs-lookup"><span data-stu-id="50896-366">Application ID URI</span></span>

<span data-ttu-id="50896-367">默认情况下，该模板通过将项目名称追加到 Azure AD 域中创建用于你的应用程序 ID URI。</span><span class="sxs-lookup"><span data-stu-id="50896-367">By default, the template creates an application ID URI for you by appending the project name to the Azure AD domain.</span></span> <span data-ttu-id="50896-368">例如，如果项目名称为`Example`，域为`contoso.onmicrosoft.com`，应用程序 ID URI 将成为`https://contoso.onmicrosoft.com/Example`。</span><span class="sxs-lookup"><span data-stu-id="50896-368">For example, if the project name is `Example` and the domain is `contoso.onmicrosoft.com`, the application ID URI becomes `https://contoso.onmicrosoft.com/Example`.</span></span> <span data-ttu-id="50896-369">如果你想要手动指定应用程序 ID URI，则展开**更多选项**部分，然后在文本框中输入应用程序 ID URI。</span><span class="sxs-lookup"><span data-stu-id="50896-369">If you want to manually specify the application ID URI, expand the **More Options** section and enter the application ID URI in the text box.</span></span> <span data-ttu-id="50896-370">应用程序 ID URI 必须以开头`https://`。</span><span class="sxs-lookup"><span data-stu-id="50896-370">The application ID URI must begin with `https://`.</span></span>

<span data-ttu-id="50896-371">默认情况下，如果已在 Azure AD 中设置应用程序具有相同应用程序 ID URI，作为一个 Visual Studio 使用项目，项目将连接到现有应用程序而不是预配一个新。</span><span class="sxs-lookup"><span data-stu-id="50896-371">By default, if an application that is already provisioned in Azure AD has the same application ID URI as the one that Visual Studio is using for the project, the project will be connected to the existing application instead of provisioning a new one.</span></span> <span data-ttu-id="50896-372">如果你想要在这种情况下设置新应用程序，清除**覆盖应用程序条目，如果已经存在一个具有相同 ID**复选框。</span><span class="sxs-lookup"><span data-stu-id="50896-372">If you want a new application to be provisioned in that case, clear the **Overwrite the application entry if one with the same ID already exists** check box.</span></span>

<span data-ttu-id="50896-373">如果**覆盖**清除复选框，并且 Visual Studio 找到具有相同的应用程序 ID URI 的现有应用程序，它通过将大量追加到它已将使用的 URI 创建一个新的 URI。</span><span class="sxs-lookup"><span data-stu-id="50896-373">If the **Overwrite** check box is cleared, and Visual Studio finds an existing application with the same application ID URI, it creates a new URI by appending a number to the URI it was going to use.</span></span> <span data-ttu-id="50896-374">例如，假定项目名称是`Example`，将文本框留空，则清除**覆盖**复选框，并且 Azure AD 租户已具有 URI 的应用程序`https://contoso.onmicrosoft.com/Example`。</span><span class="sxs-lookup"><span data-stu-id="50896-374">For example, suppose the project name is `Example`, you leave the text box blank, you clear the **Overwrite** check box, and the Azure AD tenant already has an application with the URI `https://contoso.onmicrosoft.com/Example`.</span></span> <span data-ttu-id="50896-375">在这种情况下，新的应用程序将设置与应用程序 ID URI 喜欢`https://contoso.onmicrosoft.com/Example_20130619330903`。</span><span class="sxs-lookup"><span data-stu-id="50896-375">In that case, a new application will be provisioned with an application ID URI like `https://contoso.onmicrosoft.com/Example_20130619330903`.</span></span>

#### <a name="provisioning-the-application-in-azure-ad"></a><span data-ttu-id="50896-376">设置 Azure AD 中的应用程序</span><span class="sxs-lookup"><span data-stu-id="50896-376">Provisioning the application in Azure AD</span></span>

<span data-ttu-id="50896-377">若要设置 Azure AD 中的应用程序或将项目连接到现有应用程序，Visual Studio 为域需要的全局管理员的凭据。</span><span class="sxs-lookup"><span data-stu-id="50896-377">In order to provision the application in Azure AD or connect the project to an existing application, Visual Studio needs the credentials of a global administrator for the domain.</span></span> <span data-ttu-id="50896-378">当你单击**确定**中**配置身份验证**对话框中，提示你输入的用户名和密码作为你指定的域的全局管理员。</span><span class="sxs-lookup"><span data-stu-id="50896-378">When you click **OK** in the **Configure Authentication** dialog box, you are prompted for the user name and password of a global administrator for the domain you specified.</span></span> <span data-ttu-id="50896-379">以后，当你单击**创建项目**中**新建 ASP.NET 项目**对话框中，Visual Studio 中设置 Azure AD 中的应用程序。</span><span class="sxs-lookup"><span data-stu-id="50896-379">Later, when you click **Create Project** in the **New ASP.NET Project** dialog, Visual Studio provisions the application in Azure AD.</span></span> <span data-ttu-id="50896-380">请注意，此过程的一部分 Visual Studio 客户端密钥值中嵌入过期一年后创建的 Web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="50896-380">Note that as part of this process Visual Studio embeds client secret values in the Web.config file that expire one year after creation.</span></span>

<span data-ttu-id="50896-381">有关如何创建使用的应用程序信息**云-单个组织**身份验证，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="50896-381">For information about how to create applications that use **Cloud - Single Organization** authentication, see the following resources:</span></span>

- [<span data-ttu-id="50896-382">Azure 身份验证</span><span class="sxs-lookup"><span data-stu-id="50896-382">Azure Authentication</span></span>](../2012/windows-azure-authentication.md)
- [<span data-ttu-id="50896-383">将登录名添加到 Web 应用程序使用 Azure AD</span><span class="sxs-lookup"><span data-stu-id="50896-383">Adding Sign-On to Your Web Application Using Azure AD</span></span>](https://msdn.microsoft.com/library/windowsazure/dn151790.aspx)
- [<span data-ttu-id="50896-384">开发使用 Azure Active Directory 的 ASP.NET 应用程序</span><span class="sxs-lookup"><span data-stu-id="50896-384">Developing ASP.NET Apps with Azure Active Directory</span></span>](../../../identity/overview/getting-started/developing-aspnet-apps-with-windows-azure-active-directory.md)
- [<span data-ttu-id="50896-385">保护与 Azure AD 的 ASP.NET Web API 和 Microsoft OWIN 组件</span><span class="sxs-lookup"><span data-stu-id="50896-385">Secure ASP.NET Web API with Azure AD and Microsoft OWIN Components</span></span>](https://msdn.microsoft.com/en-us/magazine/dn463788.aspx)

<span data-ttu-id="50896-386">这些教程具有尚未更新 Visual Studio 2013;哪些教程指示你手动执行的一些是在 Visual Studio 2013 中自动运行。</span><span class="sxs-lookup"><span data-stu-id="50896-386">The tutorials have not yet been updated for Visual Studio 2013; some of what the tutorials direct you to do manually is automated in Visual Studio 2013.</span></span>

<a id="orgauthmulti"></a>
### <a name="cloud---multi-organization-authentication"></a><span data-ttu-id="50896-387">云-多组织身份验证</span><span class="sxs-lookup"><span data-stu-id="50896-387">Cloud - Multi Organization Authentication</span></span>

![多个组织身份验证](creating-web-projects-in-visual-studio/_static/image25.png)

<span data-ttu-id="50896-389">如果你想要启用的用户帐户在多个 Azure AD 中定义的身份验证，请选择此选项[租户](https://technet.microsoft.com/en-us/library/jj573650.aspx)。</span><span class="sxs-lookup"><span data-stu-id="50896-389">Choose this option if you want to enable authentication for user accounts that are defined in multiple Azure AD [tenants](https://technet.microsoft.com/en-us/library/jj573650.aspx).</span></span> <span data-ttu-id="50896-390">例如，该网站为 contoso.com，而且它将可供员工的 Contoso 公司都在 contoso.onmicrosoft.com 租户中和 Fabrikam 公司的 fabrikam.onmicrosoft.com 租户中。</span><span class="sxs-lookup"><span data-stu-id="50896-390">For example, the site is contoso.com and it will be made available to employees of the Contoso Company who are in the contoso.onmicrosoft.com tenant, and employees of the Fabrikam Company who are in the fabrikam.onmicrosoft.com tenant.</span></span>

<span data-ttu-id="50896-391">你输入的设置和应用程序设置步骤是类似于[单个组织身份验证](#orgauthsingle)。</span><span class="sxs-lookup"><span data-stu-id="50896-391">The settings that you enter and the application provisioning step are similar to [single organization authentication](#orgauthsingle).</span></span>

<span data-ttu-id="50896-392">有关如何创建使用的应用程序信息**云-多组织**身份验证，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="50896-392">For information about how to create applications that use **Cloud - Multi Organization** authentication, see the following resources:</span></span>

- <span data-ttu-id="50896-393">[轻松与 Azure Active Directory，ASP.NET 的 Web 应用程序集成&amp;Visual Studio](https://blogs.msdn.com/b/active_directory_team_blog/archive/2013/06/26/improved-windows-azure-active-directory-integration-with-asp-net-amp-visual-studio.aspx) Active Directory 团队博客上。</span><span class="sxs-lookup"><span data-stu-id="50896-393">[Easy Web App Integration with Azure Active Directory, ASP.NET &amp; Visual Studio](https://blogs.msdn.com/b/active_directory_team_blog/archive/2013/06/26/improved-windows-azure-active-directory-integration-with-asp-net-amp-visual-studio.aspx) on the Active Directory Team blog.</span></span>
- <span data-ttu-id="50896-394">[开发多租户 Web 应用程序与 Azure AD](https://msdn.microsoft.com/en-us/library/windowsazure/dn151789.aspx)教程。</span><span class="sxs-lookup"><span data-stu-id="50896-394">[Developing Multi-Tenant Web Applications with Azure AD](https://msdn.microsoft.com/en-us/library/windowsazure/dn151789.aspx) tutorial.</span></span> <span data-ttu-id="50896-395">本教程尚未尚未更新 Visual Studio 2013;什么本教程将引导你手动执行的一些是在 Visual Studio 2013 中自动运行。</span><span class="sxs-lookup"><span data-stu-id="50896-395">The tutorial hasn't yet been updated for Visual Studio 2013; some of what the tutorial directs you to do manually is automated in Visual Studio 2013.</span></span>
- <span data-ttu-id="50896-396">[你必须注册订阅与你自己的多个组织 ASP.NET 应用，你可以登录之前](http://www.cloudidentity.com/blog/2013/10/26/you-have-to-sign-up-with-your-own-multiple-organizations-asp-net-app-before-you-can-sign-in/)。</span><span class="sxs-lookup"><span data-stu-id="50896-396">[You Have to Sign Up With Your Own Multiple Organizations ASP.NET App Before You Can Sign In](http://www.cloudidentity.com/blog/2013/10/26/you-have-to-sign-up-with-your-own-multiple-organizations-asp-net-app-before-you-can-sign-in/).</span></span> <span data-ttu-id="50896-397">在创建项目，使用多组织身份验证时，会遇到说明了如何解决常见的问题人员的 Vittorio Bertocci 的博客。</span><span class="sxs-lookup"><span data-stu-id="50896-397">Blog by Vittorio Bertocci that explains how to resolve a common problem people encounter when creating a project that uses multi-organization authentication.</span></span>

<a id="orgauthonprem"></a>
### <a name="on-premises-organizational-authentication"></a><span data-ttu-id="50896-398">在本地组织的身份验证</span><span class="sxs-lookup"><span data-stu-id="50896-398">On-Premises Organizational Authentication</span></span>

![在本地组织的身份验证](creating-web-projects-in-visual-studio/_static/image26.png)

<span data-ttu-id="50896-400">如果你想要启用身份验证的用户帐户的定义在 Windows Server Active Directory (AD)，并且你不想要使用 Azure AD，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="50896-400">Choose this option if you want to enable authentication for user accounts that are defined in Windows Server Active Directory (AD), and you don't want to use Azure AD.</span></span> <span data-ttu-id="50896-401">此选项可用于创建 Intranet 站点或 Internet 站点。</span><span class="sxs-lookup"><span data-stu-id="50896-401">You can use this option to create an Intranet site or an Internet site.</span></span> <span data-ttu-id="50896-402">对于 Internet 站点，使用 Active Directory 联合身份验证服务 (ADFS) 以提供对 AD 的访问。</span><span class="sxs-lookup"><span data-stu-id="50896-402">For an Internet site, use Active Directory Federation Services (ADFS) to provide access to AD.</span></span> <span data-ttu-id="50896-403">有关详细信息，请参阅[使用 Visual Studio 2013 中的本地组织身份验证选项 (ADFS) 与 ASP.NET](http://www.cloudidentity.com/blog/2014/02/12/use-the-on-premises-organizational-authentication-option-adfs-with-asp-net-in-visual-studio-2013/)。</span><span class="sxs-lookup"><span data-stu-id="50896-403">For more information, see [Use the On-Premises Organizational Authentication Option (ADFS) With ASP.NET in Visual Studio 2013](http://www.cloudidentity.com/blog/2014/02/12/use-the-on-premises-organizational-authentication-option-adfs-with-asp-net-in-visual-studio-2013/).</span></span>

<span data-ttu-id="50896-404">对于 Intranet 站点，或者你可以选择[Windows 身份验证](#winauth)而不是此选项。</span><span class="sxs-lookup"><span data-stu-id="50896-404">For an Intranet site, as an alternative you can choose [Windows Authentication](#winauth) instead of this option.</span></span> <span data-ttu-id="50896-405">为 Windows 身份验证选项，你无需提供元数据文档 URL。</span><span class="sxs-lookup"><span data-stu-id="50896-405">For the Windows Authentication option you don't have to provide a metadata document URL.</span></span> <span data-ttu-id="50896-406">但是，Windows 身份验证不使你能够控制 Active Directory 中的应用程序访问或查询目录数据。</span><span class="sxs-lookup"><span data-stu-id="50896-406">However, Windows Authentication does not give you the ability to control application access in Active Directory or to query directory data.</span></span>

#### <a name="on-premises-authority"></a><span data-ttu-id="50896-407">本地机构</span><span class="sxs-lookup"><span data-stu-id="50896-407">On-Premises Authority</span></span>

<span data-ttu-id="50896-408">输入指向元数据文档的 URL。</span><span class="sxs-lookup"><span data-stu-id="50896-408">Enter a URL that points to the metadata document.</span></span> <span data-ttu-id="50896-409">元数据文档包含颁发机构的坐标。</span><span class="sxs-lookup"><span data-stu-id="50896-409">The metadata document contains the coordinates of the authority.</span></span> <span data-ttu-id="50896-410">应用程序将使用这些坐标来驱动 web 登录流程。</span><span class="sxs-lookup"><span data-stu-id="50896-410">The application will use those coordinates to drive the web sign-on flow.</span></span>

#### <a name="application-id-uri"></a><span data-ttu-id="50896-411">应用程序 ID URI</span><span class="sxs-lookup"><span data-stu-id="50896-411">Application ID URI</span></span>

<span data-ttu-id="50896-412">提供 AD 可用于标识此应用程序，或留空以让 Visual Studio 创建一个唯一 URI。</span><span class="sxs-lookup"><span data-stu-id="50896-412">Provide a unique URI that AD can use to identify this application, or leave blank to let Visual Studio create one.</span></span>

<a id="nextsteps"></a>
## <a name="next-steps"></a><span data-ttu-id="50896-413">后续步骤</span><span class="sxs-lookup"><span data-stu-id="50896-413">Next steps</span></span>

<span data-ttu-id="50896-414">本文档提供一些基本帮助让 Visual Studio 2013 中创建新的 ASP.NET web 项目。</span><span class="sxs-lookup"><span data-stu-id="50896-414">This document has provided some basic help for creating a new ASP.NET web project in Visual Studio 2013.</span></span> <span data-ttu-id="50896-415">有关使用 for Visual Studio 进行 web 开发的详细信息，请参阅[https://www.asp.net/visual-studio/](../../index.md)。</span><span class="sxs-lookup"><span data-stu-id="50896-415">For more information about using for Visual Studio for web development, see [https://www.asp.net/visual-studio/](../../index.md).</span></span>