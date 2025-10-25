# CMakeLists.txt 行级说明

001: `cmake_minimum_required(VERSION 3.7.0)` - 指定 CMake 最低版本 3.7.0
002: `` - 空行
003: `project(otter-browser)` - 定义项目名称为 otter-browser
004: `` - 空行
005: `set(MAJOR_VERSION "1")` - 设置变量 MAJOR_VERSION 为 1
006: `set(MINOR_VERSION "0")` - 设置变量 MINOR_VERSION 为 0
007: `set(PATCH_VERSION "81")` - 设置变量 PATCH_VERSION 为 81
008: `set(WEEKLY_VERSION "" CACHE STRING "")` - 命令或参数
009: `` - 空行
010: `add_definitions(-DOTTER_VERSION_MAIN="${MAJOR_VERSION}.${MINOR_VERSION}.${PATCH_VERSION}")` - 添加编译器预处理定义
011: `` - 空行
012: `if ("${WEEKLY_VERSION}" STREQUAL "")` - 如果条件 "${WEEKLY_VERSION}" STREQUAL "" 成立，进入分支
013: `	add_definitions(-DOTTER_VERSION_CONTEXT="-dev" -DOTTER_VERSION_WEEKLY=" ")` - 添加编译器预处理定义
014: `else ()` - 否则执行该分支
015: `	add_definitions(-DOTTER_VERSION_CONTEXT=" weekly ${WEEKLY_VERSION}" -DOTTER_VERSION_WEEKLY="${WEEKLY_VERSION}")` - 添加编译器预处理定义
016: `endif ()` - 条件分支结束
017: `` - 空行
018: `if (EXISTS "${CMAKE_ROOT}/Modules/CPack.cmake")` - 如果条件 EXISTS "${CMAKE_ROOT}/Modules/CPack.cmake" 成立，进入分支
019: `	include(InstallRequiredSystemLibraries)` - 包含 InstallRequiredSystemLibraries 模块或脚本
020: `` - 空行
021: `	set(CPACK_SET_DESTDIR "on")` - 设置变量 CPACK_SET_DESTDIR 为 on
022: `	set(CPACK_PACKAGING_INSTALL_PREFIX "${CMAKE_INSTALL_PREFIX}")` - 设置变量 CPACK_PACKAGING_INSTALL_PREFIX 为 ${CMAKE_INSTALL_PREFIX}
023: `	set(CPACK_GENERATOR "DEB;RPM")` - 设置变量 CPACK_GENERATOR 为 DEB;RPM
024: `	set(CPACK_PACKAGE_DESCRIPTION_SUMMARY "Web browser controlled by the user, not vice-versa")` - 设置变量 CPACK_PACKAGE_DESCRIPTION_SUMMARY 为 Web browser controlled by the user, not vice-versa
025: `	set(CPACK_PACKAGE_VENDOR "Vendor")` - 设置变量 CPACK_PACKAGE_VENDOR 为 Vendor
026: `	set(CPACK_PACKAGE_CONTACT "Michal Dutkiewicz <michal@emdek.pl>")` - 设置变量 CPACK_PACKAGE_CONTACT 为 Michal Dutkiewicz <michal@emdek.pl>
027: `	set(CPACK_PACKAGE_VERSION_MAJOR "${MAJOR_VERSION}")` - 设置变量 CPACK_PACKAGE_VERSION_MAJOR 为 ${MAJOR_VERSION}
028: `	set(CPACK_PACKAGE_VERSION_MINOR "${MINOR_VERSION}")` - 设置变量 CPACK_PACKAGE_VERSION_MINOR 为 ${MINOR_VERSION}
029: `	set(CPACK_PACKAGE_VERSION_PATCH "${PATCH_VERSION}")` - 设置变量 CPACK_PACKAGE_VERSION_PATCH 为 ${PATCH_VERSION}
030: `	set(CPACK_PACKAGE_NAME "otter-browser")` - 设置变量 CPACK_PACKAGE_NAME 为 otter-browser
031: `	set(CPACK_PACKAGE_FILE_NAME "${CPACK_PACKAGE_NAME}_${MAJOR_VERSION}.${MINOR_VERSION}.${CPACK_PACKAGE_VERSION_PATCH}")` - 设置变量 CPACK_PACKAGE_FILE_NAME 为 ${CPACK_PACKAGE_NAME}_${MAJOR_VERSION}.${MINOR_VERSION}.${CPACK_PACKAGE_VERSION_PATCH}
032: `	set(CPACK_SOURCE_PACKAGE_FILE_NAME "${CPACK_PACKAGE_NAME}_${MAJOR_VERSION}.${MINOR_VERSION}.${CPACK_PACKAGE_VERSION_PATCH}")` - 设置变量 CPACK_SOURCE_PACKAGE_FILE_NAME 为 ${CPACK_PACKAGE_NAME}_${MAJOR_VERSION}.${MINOR_VERSION}.${CPACK_PACKAGE_VERSION_PATCH}
033: `	set(CPACK_DEBIAN_PACKAGE_DEPENDS "libhunspell-1.5-0 (>= 1.5.1), libqt5multimedia5 (>=5.15.0), libqt5qml5 (>=5.15.0), libqt5svg5 (>=5.15.0), libqt5webkit5 (>=5.212.0~alpha2)")` - 设置变量 CPACK_DEBIAN_PACKAGE_DEPENDS 为 libhunspell-1.5-0 (>= 1.5.1), libqt5multimedia5 (>=5.15.0), libqt5qml5 (>=5.15.0), libqt5svg5 (>=5.15.0), libqt5webkit5 (>=5.212.0~alpha2)
034: `	set(CPACK_DEBIAN_PACKAGE_RECOMMENDS "gstreamer1.0-plugins-base, gstreamer1.0-plugins-good")` - 设置变量 CPACK_DEBIAN_PACKAGE_RECOMMENDS 为 gstreamer1.0-plugins-base, gstreamer1.0-plugins-good
035: `	set(CPACK_DEBIAN_PACKAGE_PRIORITY "optional")` - 设置变量 CPACK_DEBIAN_PACKAGE_PRIORITY 为 optional
036: `	set(CPACK_DEBIAN_PACKAGE_SECTION "web")` - 设置变量 CPACK_DEBIAN_PACKAGE_SECTION 为 web
037: `	set(CPACK_DEBIAN_ARCHITECTURE ${CMAKE_SYSTEM_PROCESSOR})` - 设置变量 CPACK_DEBIAN_ARCHITECTURE 为 ${CMAKE_SYSTEM_PROCESSOR}
038: `	set(CPACK_COMPONENTS_ALL Libraries ApplicationData)` - 设置变量 CPACK_COMPONENTS_ALL 为 Libraries ApplicationData
039: `	set(CPACK_RPM_EXCLUDE_FROM_AUTO_FILELIST_ADDITION` - 命令或参数
040: `		${CMAKE_INSTALL_MANDIR}/man1` - 命令或参数
041: `		${CMAKE_INSTALL_PREFIX}/share/applications` - 命令或参数
042: `		${CMAKE_INSTALL_PREFIX}/share/icons` - 命令或参数
043: `		${CMAKE_INSTALL_PREFIX}/share/icons/hicolor` - 命令或参数
044: `		${CMAKE_INSTALL_PREFIX}/share/icons/hicolor/16x16` - 命令或参数
045: `		${CMAKE_INSTALL_PREFIX}/share/icons/hicolor/32x32` - 命令或参数
046: `		${CMAKE_INSTALL_PREFIX}/share/icons/hicolor/48x48` - 命令或参数
047: `		${CMAKE_INSTALL_PREFIX}/share/icons/hicolor/64x64` - 命令或参数
048: `		${CMAKE_INSTALL_PREFIX}/share/icons/hicolor/128x128` - 命令或参数
049: `		${CMAKE_INSTALL_PREFIX}/share/icons/hicolor/256x256` - 命令或参数
050: `		${CMAKE_INSTALL_PREFIX}/share/icons/hicolor/16x16/apps` - 命令或参数
051: `		${CMAKE_INSTALL_PREFIX}/share/icons/hicolor/32x32/apps` - 命令或参数
052: `		${CMAKE_INSTALL_PREFIX}/share/icons/hicolor/48x48/apps` - 命令或参数
053: `		${CMAKE_INSTALL_PREFIX}/share/icons/hicolor/64x64/apps` - 命令或参数
054: `		${CMAKE_INSTALL_PREFIX}/share/icons/hicolor/128x128/apps` - 命令或参数
055: `		${CMAKE_INSTALL_PREFIX}/share/icons/hicolor/256x256/apps` - 命令或参数
056: `	)` - 命令或参数
057: `` - 空行
058: `	include(CPack)` - 包含 CPack 模块或脚本
059: `endif ()` - 条件分支结束
060: `` - 空行
061: `set(CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/cmake)` - 设置变量 CMAKE_MODULE_PATH 为 ${CMAKE_CURRENT_SOURCE_DIR}/cmake
062: `set(CMAKE_INCLUDE_CURRENT_DIR ON)` - 设置变量 CMAKE_INCLUDE_CURRENT_DIR 为 ON
063: `set(CMAKE_AUTOMOC ON)` - 设置变量 CMAKE_AUTOMOC 为 ON
064: `set(CMAKE_CXX_EXTENSIONS OFF)` - 设置变量 CMAKE_CXX_EXTENSIONS 为 OFF
065: `set(CMAKE_CXX_STANDARD 11)` - 设置变量 CMAKE_CXX_STANDARD 为 11
066: `set(CMAKE_CXX_STANDARD_REQUIRED ON)` - 设置变量 CMAKE_CXX_STANDARD_REQUIRED 为 ON
067: `` - 空行
068: `include(FeatureSummary)` - 包含 FeatureSummary 模块或脚本
069: `include(GNUInstallDirs)` - 包含 GNUInstallDirs 模块或脚本
070: `` - 空行
071: `option(ALLOW_WITHOUT_WEB_BACKENDS "Allow to build without any web backends (build testing only)" OFF)` - 定义选项 ALLOW_WITHOUT_WEB_BACKENDS：Allow to build without any web backends (build testing only)，默认OFF
072: `option(ENABLE_QTWEBENGINE "Enable QtWebEngine backend (requires QtWebEngine 5.15)" ON)` - 定义选项 ENABLE_QTWEBENGINE：Enable QtWebEngine backend (requires QtWebEngine 5.15)，默认ON
073: `option(ENABLE_QTWEBKIT "Enable QtWebKit backend (requires QtWebKit 5.212)" ON)` - 定义选项 ENABLE_QTWEBKIT：Enable QtWebKit backend (requires QtWebKit 5.212)，默认ON
074: `option(ENABLE_CRASH_REPORTS "Enable built-in crash reporting (official builds only)" OFF)` - 定义选项 ENABLE_CRASH_REPORTS：Enable built-in crash reporting (official builds only)，默认OFF
075: `option(ENABLE_DBUS "Enable D-Bus based integration for notifications (only freedesktop.org compatible platforms)" ON)` - 定义选项 ENABLE_DBUS：Enable D-Bus based integration for notifications (only freedesktop.org compatible platforms)，默认ON
076: `option(ENABLE_SPELLCHECK "Enable Hunspell based spell checking" ON)` - 定义选项 ENABLE_SPELLCHECK：Enable Hunspell based spell checking，默认ON
077: `` - 空行
078: `find_package(Qt5 5.15.0 REQUIRED COMPONENTS Core Gui Multimedia Network PrintSupport Qml Svg Widgets)` - 查找并加载包：Qt5 5.15.0 REQUIRED COMPONENTS Core Gui Multimedia Network PrintSupport Qml Svg Widgets
079: `find_package(Hunspell 1.5.0 QUIET)` - 查找并加载包：Hunspell 1.5.0 QUIET
080: `` - 空行
081: `set_package_properties(Hunspell PROPERTIES URL "https://hunspell.github.io/" DESCRIPTION "Generic spell checking support" TYPE OPTIONAL)` - 设置包属性
082: `` - 空行
083: `set(OTTER_SOURCES` - 命令或参数
084: `	src/main.cpp` - 源文件路径
085: `	src/core/ActionExecutor.cpp` - 源文件路径
086: `	src/core/ActionsManager.cpp` - 源文件路径
087: `	src/core/AdblockContentFiltersProfile.cpp` - 源文件路径
088: `	src/core/AddonsManager.cpp` - 源文件路径
089: `	src/core/Application.cpp` - 源文件路径
090: `	src/core/BookmarksManager.cpp` - 源文件路径
091: `	src/core/BookmarksModel.cpp` - 源文件路径
092: `	src/core/ContentFiltersManager.cpp` - 源文件路径
093: `	src/core/Console.cpp` - 源文件路径
094: `	src/core/CookieJar.cpp` - 源文件路径
095: `	src/core/DataExchanger.cpp` - 源文件路径
096: `	src/core/FeedParser.cpp` - 源文件路径
097: `	src/core/FeedsManager.cpp` - 源文件路径
098: `	src/core/FeedsModel.cpp` - 源文件路径
099: `	src/core/GesturesController.cpp` - 源文件路径
100: `	src/core/GesturesManager.cpp` - 源文件路径
101: `	src/core/HandlersManager.cpp` - 源文件路径
102: `	src/core/HistoryManager.cpp` - 源文件路径
103: `	src/core/HistoryModel.cpp` - 源文件路径
104: `	src/core/IniSettings.cpp` - 源文件路径
105: `	src/core/InputInterpreter.cpp` - 源文件路径
106: `	src/core/ItemModel.cpp` - 源文件路径
107: `	src/core/Job.cpp` - 源文件路径
108: `	src/core/JsonSettings.cpp` - 源文件路径
109: `	src/core/ListingNetworkReply.cpp` - 源文件路径
110: `	src/core/LocalListingNetworkReply.cpp` - 源文件路径
111: `	src/core/LongTermTimer.cpp` - 源文件路径
112: `	src/core/Migrator.cpp` - 源文件路径
113: `	src/core/NetworkAutomaticProxy.cpp` - 源文件路径
114: `	src/core/NetworkCache.cpp` - 源文件路径
115: `	src/core/NetworkManager.cpp` - 源文件路径
116: `	src/core/NetworkManagerFactory.cpp` - 源文件路径
117: `	src/core/NetworkProxyFactory.cpp` - 源文件路径
118: `	src/core/NotesManager.cpp` - 源文件路径
119: `	src/core/NotificationsManager.cpp` - 源文件路径
120: `	src/core/PasswordsManager.cpp` - 源文件路径
121: `	src/core/PasswordsStorageBackend.cpp` - 源文件路径
122: `	src/core/PlatformIntegration.cpp` - 源文件路径
123: `	src/core/SearchEnginesManager.cpp` - 源文件路径
124: `	src/core/SearchSuggester.cpp` - 源文件路径
125: `	src/core/SessionModel.cpp` - 源文件路径
126: `	src/core/SessionsManager.cpp` - 源文件路径
127: `	src/core/SettingsManager.cpp` - 源文件路径
128: `	src/core/SpellCheckManager.cpp` - 源文件路径
129: `	src/core/TasksManager.cpp` - 源文件路径
130: `	src/core/ThemesManager.cpp` - 源文件路径
131: `	src/core/ToolBarsManager.cpp` - 源文件路径
132: `	src/core/TransfersManager.cpp` - 源文件路径
133: `	src/core/UpdateChecker.cpp` - 源文件路径
134: `	src/core/Updater.cpp` - 源文件路径
135: `	src/core/UserScript.cpp` - 源文件路径
136: `	src/core/Utils.cpp` - 源文件路径
137: `	src/core/WebBackend.cpp` - 源文件路径
138: `	src/ui/AcceptCookieDialog.cpp` - 源文件路径
139: `	src/ui/Action.cpp` - 源文件路径
140: `	src/ui/ActionComboBoxWidget.cpp` - 源文件路径
141: `	src/ui/ActionParametersDialog.cpp` - 源文件路径
142: `	src/ui/Animation.cpp` - 源文件路径
143: `	src/ui/ApplicationComboBoxWidget.cpp` - 源文件路径
144: `	src/ui/AuthenticationDialog.cpp` - 源文件路径
145: `	src/ui/BookmarkPropertiesDialog.cpp` - 源文件路径
146: `	src/ui/BookmarksComboBoxWidget.cpp` - 源文件路径
147: `	src/ui/BookmarksImportOptionsWidget.cpp` - 源文件路径
148: `	src/ui/CategoriesTabWidget.cpp` - 源文件路径
149: `	src/ui/CertificateDialog.cpp` - 源文件路径
150: `	src/ui/ClearHistoryDialog.cpp` - 源文件路径
151: `	src/ui/ColorWidget.cpp` - 源文件路径
152: `	src/ui/ComboBoxWidget.cpp` - 源文件路径
153: `	src/ui/ContentBlockingProfileDialog.cpp` - 源文件路径
154: `	src/ui/ContentFiltersViewWidget.cpp` - 源文件路径
155: `	src/ui/ContentsDialog.cpp` - 源文件路径
156: `	src/ui/ContentsWidget.cpp` - 源文件路径
157: `	src/ui/CookiePropertiesDialog.cpp` - 源文件路径
158: `	src/ui/DataExchangerDialog.cpp` - 源文件路径
159: `	src/ui/DateTimeTextLabelWidget.cpp` - 源文件路径
160: `	src/ui/DiagnosticReportDialog.cpp` - 源文件路径
161: `	src/ui/Dialog.cpp` - 源文件路径
162: `	src/ui/FeedPropertiesDialog.cpp` - 源文件路径
163: `	src/ui/FeedsComboBoxWidget.cpp` - 源文件路径
164: `	src/ui/FilePathWidget.cpp` - 源文件路径
165: `	src/ui/HeaderWidget.cpp` - 源文件路径
166: `	src/ui/IconWidget.cpp` - 源文件路径
167: `	src/ui/ImagePropertiesDialog.cpp` - 源文件路径
168: `	src/ui/InlineListWidget.cpp` - 源文件路径
169: `	src/ui/ItemDelegate.cpp` - 源文件路径
170: `	src/ui/ItemViewWidget.cpp` - 源文件路径
171: `	src/ui/LineEditWidget.cpp` - 源文件路径
172: `	src/ui/LocaleDialog.cpp` - 源文件路径
173: `	src/ui/MainWindow.cpp` - 源文件路径
174: `	src/ui/MasterPasswordDialog.cpp` - 源文件路径
175: `	src/ui/Menu.cpp` - 源文件路径
176: `	src/ui/MenuBarWidget.cpp` - 源文件路径
177: `	src/ui/MetaDataDialog.cpp` - 源文件路径
178: `	src/ui/NotificationDialog.cpp` - 源文件路径
179: `	src/ui/OpenAddressDialog.cpp` - 源文件路径
180: `	src/ui/OpenBookmarkDialog.cpp` - 源文件路径
181: `	src/ui/OptionWidget.cpp` - 源文件路径
182: `	src/ui/PassiveNotificationWidget.cpp` - 源文件路径
183: `	src/ui/PreferencesDialog.cpp` - 源文件路径
184: `	src/ui/PreviewWidget.cpp` - 源文件路径
185: `	src/ui/ProgressBarWidget.cpp` - 源文件路径
186: `	src/ui/ProxyModel.cpp` - 源文件路径
187: `	src/ui/QuickResponseCodeDialog.cpp` - 源文件路径
188: `	src/ui/QuickResponseCodeWidget.cpp` - 源文件路径
189: `	src/ui/ReloadTimeDialog.cpp` - 源文件路径
190: `	src/ui/ResizerWidget.cpp` - 源文件路径
191: `	src/ui/SaveSessionDialog.cpp` - 源文件路径
192: `	src/ui/SearchEnginePropertiesDialog.cpp` - 源文件路径
193: `	src/ui/SessionsManagerDialog.cpp` - 源文件路径
194: `	src/ui/SidebarWidget.cpp` - 源文件路径
195: `	src/ui/SourceEditWidget.cpp` - 源文件路径
196: `	src/ui/SourceViewerWebWidget.cpp` - 源文件路径
197: `	src/ui/SplitterWidget.cpp` - 源文件路径
198: `	src/ui/StartupDialog.cpp` - 源文件路径
199: `	src/ui/StatusBarWidget.cpp` - 源文件路径
200: `	src/ui/Style.cpp` - 源文件路径
201: `	src/ui/SyntaxHighlighter.cpp` - 源文件路径
202: `	src/ui/TabBarWidget.cpp` - 源文件路径
203: `	src/ui/TabSwitcherWidget.cpp` - 源文件路径
204: `	src/ui/TextBrowserWidget.cpp` - 源文件路径
205: `	src/ui/TextEditWidget.cpp` - 源文件路径
206: `	src/ui/TextLabelWidget.cpp` - 源文件路径
207: `	src/ui/ToolBarDialog.cpp` - 源文件路径
208: `	src/ui/ToolBarDropZoneWidget.cpp` - 源文件路径
209: `	src/ui/ToolBarWidget.cpp` - 源文件路径
210: `	src/ui/ToolButtonWidget.cpp` - 源文件路径
211: `	src/ui/TransferDialog.cpp` - 源文件路径
212: `	src/ui/TrayIcon.cpp` - 源文件路径
213: `	src/ui/UpdateCheckerDialog.cpp` - 源文件路径
214: `	src/ui/WebsiteInformationDialog.cpp` - 源文件路径
215: `	src/ui/WebsitePreferencesDialog.cpp` - 源文件路径
216: `	src/ui/WebWidget.cpp` - 源文件路径
217: `	src/ui/WidgetFactory.cpp` - 源文件路径
218: `	src/ui/Window.cpp` - 源文件路径
219: `	src/ui/WorkspaceWidget.cpp` - 源文件路径
220: `	src/ui/preferences/AcceptLanguageDialog.cpp` - 源文件路径
221: `	src/ui/preferences/CookiesExceptionsDialog.cpp` - 源文件路径
222: `	src/ui/preferences/MouseProfileDialog.cpp` - 源文件路径
223: `	src/ui/preferences/ProxyPropertiesDialog.cpp` - 源文件路径
224: `	src/ui/preferences/UserAgentPropertiesDialog.cpp` - 源文件路径
225: `	src/modules/backends/passwords/file/FilePasswordsStorageBackend.cpp` - 源文件路径
226: `	src/modules/exporters/html/HtmlBookmarksExportDataExchanger.cpp` - 源文件路径
227: `	src/modules/exporters/xbel/XbelBookmarksExportDataExchanger.cpp` - 源文件路径
228: `	src/modules/importers/html/HtmlBookmarksImportDataExchanger.cpp` - 源文件路径
229: `	src/modules/importers/opera/OperaBookmarksImportDataExchanger.cpp` - 源文件路径
230: `	src/modules/importers/opera/OperaNotesImportDataExchanger.cpp` - 源文件路径
231: `	src/modules/importers/opera/OperaSearchEnginesImportDataExchanger.cpp` - 源文件路径
232: `	src/modules/importers/opera/OperaSessionImportDataExchanger.cpp` - 源文件路径
233: `	src/modules/importers/opml/OpmlImportDataExchanger.cpp` - 源文件路径
234: `	src/modules/importers/opml/OpmlImportOptionsWidget.cpp` - 源文件路径
235: `	src/modules/widgets/action/ActionWidget.cpp` - 源文件路径
236: `	src/modules/widgets/address/AddressCompletionModel.cpp` - 源文件路径
237: `	src/modules/widgets/address/AddressWidget.cpp` - 源文件路径
238: `	src/modules/widgets/bookmark/BookmarkWidget.cpp` - 源文件路径
239: `	src/modules/widgets/configurationOption/ConfigurationOptionWidget.cpp` - 源文件路径
240: `	src/modules/widgets/contentBlockingInformation/ContentBlockingInformationWidget.cpp` - 源文件路径
241: `	src/modules/widgets/errorConsole/ErrorConsoleWidget.cpp` - 源文件路径
242: `	src/modules/widgets/menuButton/MenuButtonWidget.cpp` - 源文件路径
243: `	src/modules/widgets/panelChooser/PanelChooserWidget.cpp` - 源文件路径
244: `	src/modules/widgets/privateWindowIndicator/PrivateWindowIndicatorWidget.cpp` - 源文件路径
245: `	src/modules/widgets/progressInformation/ProgressInformationWidget.cpp` - 源文件路径
246: `	src/modules/widgets/search/SearchWidget.cpp` - 源文件路径
247: `	src/modules/widgets/statusMessage/StatusMessageWidget.cpp` - 源文件路径
248: `	src/modules/widgets/transfers/TransfersWidget.cpp` - 源文件路径
249: `	src/modules/widgets/zoom/ZoomWidget.cpp` - 源文件路径
250: `	src/modules/windows/actions/ActionsContentsWidget.cpp` - 源文件路径
251: `	src/modules/windows/addons/AddonsContentsWidget.cpp` - 源文件路径
252: `	src/modules/windows/addons/AddonsPage.cpp` - 源文件路径
253: `	src/modules/windows/addons/DictionariesPage.cpp` - 源文件路径
254: `	src/modules/windows/addons/UserScriptsPage.cpp` - 源文件路径
255: `	src/modules/windows/bookmarks/BookmarksContentsWidget.cpp` - 源文件路径
256: `	src/modules/windows/cache/CacheContentsWidget.cpp` - 源文件路径
257: `	src/modules/windows/configuration/ConfigurationContentsWidget.cpp` - 源文件路径
258: `	src/modules/windows/configuration/OverridesDialog.cpp` - 源文件路径
259: `	src/modules/windows/contentFilters/ContentFiltersContentsWidget.cpp` - 源文件路径
260: `	src/modules/windows/cookies/CookiesContentsWidget.cpp` - 源文件路径
261: `	src/modules/windows/history/HistoryContentsWidget.cpp` - 源文件路径
262: `	src/modules/windows/feeds/FeedsContentsWidget.cpp` - 源文件路径
263: `	src/modules/windows/links/LinksContentsWidget.cpp` - 源文件路径
264: `	src/modules/windows/notes/NotesContentsWidget.cpp` - 源文件路径
265: `	src/modules/windows/pageInformation/PageInformationContentsWidget.cpp` - 源文件路径
266: `	src/modules/windows/passwords/PasswordsContentsWidget.cpp` - 源文件路径
267: `	src/modules/windows/preferences/AdvancedPreferencesPage.cpp` - 源文件路径
268: `	src/modules/windows/preferences/ContentPreferencesPage.cpp` - 源文件路径
269: `	src/modules/windows/preferences/GeneralPreferencesPage.cpp` - 源文件路径
270: `	src/modules/windows/preferences/InputPreferencesPage.cpp` - 源文件路径
271: `	src/modules/windows/preferences/PreferencesContentsWidget.cpp` - 源文件路径
272: `	src/modules/windows/preferences/PrivacyPreferencesPage.cpp` - 源文件路径
273: `	src/modules/windows/preferences/SearchPreferencesPage.cpp` - 源文件路径
274: `	src/modules/windows/preferences/WebsitesPreferencesPage.cpp` - 源文件路径
275: `	src/modules/windows/tabHistory/TabHistoryContentsWidget.cpp` - 源文件路径
276: `	src/modules/windows/transfers/TransfersContentsWidget.cpp` - 源文件路径
277: `	src/modules/windows/web/PasswordBarWidget.cpp` - 源文件路径
278: `	src/modules/windows/web/PermissionBarWidget.cpp` - 源文件路径
279: `	src/modules/windows/web/PopupsBarWidget.cpp` - 源文件路径
280: `	src/modules/windows/web/ProgressToolBarWidget.cpp` - 源文件路径
281: `	src/modules/windows/web/SearchBarWidget.cpp` - 源文件路径
282: `	src/modules/windows/web/SelectPasswordDialog.cpp` - 源文件路径
283: `	src/modules/windows/web/StartPageModel.cpp` - 源文件路径
284: `	src/modules/windows/web/StartPagePreferencesDialog.cpp` - 源文件路径
285: `	src/modules/windows/web/StartPageWidget.cpp` - 源文件路径
286: `	src/modules/windows/web/WebContentsWidget.cpp` - 源文件路径
287: `	src/modules/windows/windows/WindowsContentsWidget.cpp` - 源文件路径
288: `	3rdparty/columnresizer/ColumnResizer.cpp` - 命令或参数
289: `	3rdparty/mousegestures/MouseGestures.cpp` - 命令或参数
290: `	3rdparty/qrcodegen/qrcodegen.cpp` - 命令或参数
291: `)` - 命令或参数
292: `` - 空行
293: `qt5_add_resources(OTTER_RESOURCES` - 命令或参数
294: `	resources/resources.qrc` - 源文件路径
295: `)` - 命令或参数
296: `` - 空行
297: `qt5_wrap_ui(OTTER_UI` - 命令或参数
298: `	src/ui/AcceptCookieDialog.ui` - 源文件路径
299: `	src/ui/ActionParametersDialog.ui` - 源文件路径
300: `	src/ui/AuthenticationDialog.ui` - 源文件路径
301: `	src/ui/BookmarkPropertiesDialog.ui` - 源文件路径
302: `	src/ui/BookmarksImportOptionsWidget.ui` - 源文件路径
303: `	src/ui/CertificateDialog.ui` - 源文件路径
304: `	src/ui/ClearHistoryDialog.ui` - 源文件路径
305: `	src/ui/ContentBlockingProfileDialog.ui` - 源文件路径
306: `	src/ui/CookiePropertiesDialog.ui` - 源文件路径
307: `	src/ui/DataExchangerDialog.ui` - 源文件路径
308: `	src/ui/DiagnosticReportDialog.ui` - 源文件路径
309: `	src/ui/FeedPropertiesDialog.ui` - 源文件路径
310: `	src/ui/ImagePropertiesDialog.ui` - 源文件路径
311: `	src/ui/LocaleDialog.ui` - 源文件路径
312: `	src/ui/MainWindow.ui` - 源文件路径
313: `	src/ui/MasterPasswordDialog.ui` - 源文件路径
314: `	src/ui/MetaDataDialog.ui` - 源文件路径
315: `	src/ui/OpenAddressDialog.ui` - 源文件路径
316: `	src/ui/OpenBookmarkDialog.ui` - 源文件路径
317: `	src/ui/PreferencesDialog.ui` - 源文件路径
318: `	src/ui/QuickResponseCodeDialog.ui` - 源文件路径
319: `	src/ui/ReloadTimeDialog.ui` - 源文件路径
320: `	src/ui/SaveSessionDialog.ui` - 源文件路径
321: `	src/ui/SearchEnginePropertiesDialog.ui` - 源文件路径
322: `	src/ui/SessionsManagerDialog.ui` - 源文件路径
323: `	src/ui/SidebarWidget.ui` - 源文件路径
324: `	src/ui/StartupDialog.ui` - 源文件路径
325: `	src/ui/ToolBarDialog.ui` - 源文件路径
326: `	src/ui/TransferDialog.ui` - 源文件路径
327: `	src/ui/UpdateCheckerDialog.ui` - 源文件路径
328: `	src/ui/WebsiteInformationDialog.ui` - 源文件路径
329: `	src/ui/WebsitePreferencesDialog.ui` - 源文件路径
330: `	src/ui/preferences/AcceptLanguageDialog.ui` - 源文件路径
331: `	src/ui/preferences/CookiesExceptionsDialog.ui` - 源文件路径
332: `	src/ui/preferences/MouseProfileDialog.ui` - 源文件路径
333: `	src/ui/preferences/ProxyPropertiesDialog.ui` - 源文件路径
334: `	src/ui/preferences/UserAgentPropertiesDialog.ui` - 源文件路径
335: `	src/modules/importers/opml/OpmlImportOptionsWidget.ui` - 源文件路径
336: `	src/modules/widgets/errorConsole/ErrorConsoleWidget.ui` - 源文件路径
337: `	src/modules/windows/actions/ActionsContentsWidget.ui` - 源文件路径
338: `	src/modules/windows/addons/AddonsContentsWidget.ui` - 源文件路径
339: `	src/modules/windows/addons/AddonsPage.ui` - 源文件路径
340: `	src/modules/windows/bookmarks/BookmarksContentsWidget.ui` - 源文件路径
341: `	src/modules/windows/cache/CacheContentsWidget.ui` - 源文件路径
342: `	src/modules/windows/configuration/ConfigurationContentsWidget.ui` - 源文件路径
343: `	src/modules/windows/configuration/OverridesDialog.ui` - 源文件路径
344: `	src/modules/windows/contentFilters/ContentFiltersContentsWidget.ui` - 源文件路径
345: `	src/modules/windows/cookies/CookiesContentsWidget.ui` - 源文件路径
346: `	src/modules/windows/feeds/FeedsContentsWidget.ui` - 源文件路径
347: `	src/modules/windows/history/HistoryContentsWidget.ui` - 源文件路径
348: `	src/modules/windows/links/LinksContentsWidget.ui` - 源文件路径
349: `	src/modules/windows/notes/NotesContentsWidget.ui` - 源文件路径
350: `	src/modules/windows/pageInformation/PageInformationContentsWidget.ui` - 源文件路径
351: `	src/modules/windows/passwords/PasswordsContentsWidget.ui` - 源文件路径
352: `	src/modules/windows/preferences/AdvancedPreferencesPage.ui` - 源文件路径
353: `	src/modules/windows/preferences/ContentPreferencesPage.ui` - 源文件路径
354: `	src/modules/windows/preferences/GeneralPreferencesPage.ui` - 源文件路径
355: `	src/modules/windows/preferences/InputPreferencesPage.ui` - 源文件路径
356: `	src/modules/windows/preferences/PreferencesContentsWidget.ui` - 源文件路径
357: `	src/modules/windows/preferences/PrivacyPreferencesPage.ui` - 源文件路径
358: `	src/modules/windows/preferences/SearchPreferencesPage.ui` - 源文件路径
359: `	src/modules/windows/preferences/WebsitesPreferencesPage.ui` - 源文件路径
360: `	src/modules/windows/tabHistory/TabHistoryContentsWidget.ui` - 源文件路径
361: `	src/modules/windows/transfers/TransfersContentsWidget.ui` - 源文件路径
362: `	src/modules/windows/web/PasswordBarWidget.ui` - 源文件路径
363: `	src/modules/windows/web/PermissionBarWidget.ui` - 源文件路径
364: `	src/modules/windows/web/PopupsBarWidget.ui` - 源文件路径
365: `	src/modules/windows/web/SearchBarWidget.ui` - 源文件路径
366: `	src/modules/windows/web/SelectPasswordDialog.ui` - 源文件路径
367: `	src/modules/windows/web/StartPagePreferencesDialog.ui` - 源文件路径
368: `	src/modules/windows/windows/WindowsContentsWidget.ui` - 源文件路径
369: `)` - 命令或参数
370: `` - 空行
371: `foreach (_dir ${Qt5Widgets_PRIVATE_INCLUDE_DIRS})` - 循环开始
372: `	if (EXISTS "${_dir}/private/qpixmapfilter_p.h")` - 如果条件 EXISTS "${_dir}/private/qpixmapfilter_p.h" 成立，进入分支
373: `		add_definitions(-DOTTER_ENABLE_STARTPAGEBLUR)` - 添加编译器预处理定义
374: `		include_directories(${Qt5Widgets_PRIVATE_INCLUDE_DIRS})` - 命令或参数
375: `` - 空行
376: `		break ()` - 命令或参数
377: `	endif ()` - 条件分支结束
378: `endforeach ()` - 循环结束
379: `` - 空行
380: `if (ENABLE_QTWEBENGINE)` - 如果条件 ENABLE_QTWEBENGINE 成立，进入分支
381: `	include(src/modules/backends/web/qtwebengine/CMakeLists.txt)` - 包含 src/modules/backends/web/qtwebengine/CMakeLists.txt 模块或脚本
382: `endif ()` - 条件分支结束
383: `` - 空行
384: `if (ENABLE_QTWEBKIT)` - 如果条件 ENABLE_QTWEBKIT 成立，进入分支
385: `	include(src/modules/backends/web/qtwebkit/CMakeLists.txt)` - 包含 src/modules/backends/web/qtwebkit/CMakeLists.txt 模块或脚本
386: `endif ()` - 条件分支结束
387: `` - 空行
388: `if (ENABLE_CRASH_REPORTS)` - 如果条件 ENABLE_CRASH_REPORTS 成立，进入分支
389: `	add_definitions(-DOTTER_ENABLE_CRASH_REPORTS)` - 添加编译器预处理定义
390: `	include_directories(${CMAKE_SOURCE_DIR}/3rdparty/breakpad/src/)` - 命令或参数
391: `` - 空行
392: `	if (WIN32)` - 如果条件 WIN32 成立，进入分支
393: `		set(OTTER_SOURCES` - 命令或参数
394: `			${OTTER_SOURCES}` - 命令或参数
395: `			3rdparty/breakpad/src/common/windows/guid_string.cc` - 命令或参数
396: `			3rdparty/breakpad/src/client/windows/crash_generation/crash_generation_client.cc` - 命令或参数
397: `			3rdparty/breakpad/src/client/windows/handler/exception_handler.cc` - 命令或参数
398: `		)` - 命令或参数
399: `	elseif (CMAKE_SYSTEM_NAME MATCHES "Linux")` - 否则如果 CMAKE_SYSTEM_NAME MATCHES "Linux" 成立
400: `		set(OTTER_SOURCES` - 命令或参数
401: `			${OTTER_SOURCES}` - 命令或参数
402: `			3rdparty/breakpad/src/client/minidump_file_writer.cc` - 命令或参数
403: `			3rdparty/breakpad/src/client/linux/crash_generation/crash_generation_client.cc` - 命令或参数
404: `			3rdparty/breakpad/src/client/linux/dump_writer_common/thread_info.cc` - 命令或参数
405: `			3rdparty/breakpad/src/client/linux/dump_writer_common/ucontext_reader.cc` - 命令或参数
406: `			3rdparty/breakpad/src/client/linux/handler/exception_handler.cc` - 命令或参数
407: `			3rdparty/breakpad/src/client/linux/handler/minidump_descriptor.cc` - 命令或参数
408: `			3rdparty/breakpad/src/client/linux/log/log.cc` - 命令或参数
409: `			3rdparty/breakpad/src/client/linux/microdump_writer/microdump_writer.cc` - 命令或参数
410: `			3rdparty/breakpad/src/client/linux/minidump_writer/linux_core_dumper.cc` - 命令或参数
411: `			3rdparty/breakpad/src/client/linux/minidump_writer/linux_dumper.cc` - 命令或参数
412: `			3rdparty/breakpad/src/client/linux/minidump_writer/linux_ptrace_dumper.cc` - 命令或参数
413: `			3rdparty/breakpad/src/client/linux/minidump_writer/minidump_writer.cc` - 命令或参数
414: `			3rdparty/breakpad/src/common/convert_UTF.c` - 命令或参数
415: `			3rdparty/breakpad/src/common/md5.cc` - 命令或参数
416: `			3rdparty/breakpad/src/common/string_conversion.cc` - 命令或参数
417: `			3rdparty/breakpad/src/common/linux/elf_core_dump.cc` - 命令或参数
418: `			3rdparty/breakpad/src/common/linux/elfutils.cc` - 命令或参数
419: `			3rdparty/breakpad/src/common/linux/file_id.cc` - 命令或参数
420: `			3rdparty/breakpad/src/common/linux/guid_creator.cc` - 命令或参数
421: `			3rdparty/breakpad/src/common/linux/linux_libc_support.cc` - 命令或参数
422: `			3rdparty/breakpad/src/common/linux/memory_mapped_file.cc` - 命令或参数
423: `			3rdparty/breakpad/src/common/linux/safe_readlink.cc` - 命令或参数
424: `		)` - 命令或参数
425: `	endif ()` - 条件分支结束
426: `endif ()` - 条件分支结束
427: `` - 空行
428: `if (TARGET Hunspell::Hunspell AND ENABLE_SPELLCHECK)` - 如果条件 TARGET Hunspell::Hunspell AND ENABLE_SPELLCHECK 成立，进入分支
429: `	add_definitions(-DOTTER_ENABLE_SPELLCHECK)` - 添加编译器预处理定义
430: `	include_directories(Hunspell::Hunspell)` - 命令或参数
431: `` - 空行
432: `	set(OTTER_SOURCES` - 命令或参数
433: `		${OTTER_SOURCES}` - 命令或参数
434: `		3rdparty/sonnet/src/core/client.cpp` - 命令或参数
435: `		3rdparty/sonnet/src/core/loader.cpp` - 命令或参数
436: `		3rdparty/sonnet/src/core/speller.cpp` - 命令或参数
437: `		3rdparty/sonnet/src/core/spellerplugin.cpp` - 命令或参数
438: `		3rdparty/sonnet/src/core/settings.cpp` - 命令或参数
439: `		3rdparty/sonnet/src/core/textbreaks.cpp` - 命令或参数
440: `		3rdparty/sonnet/src/core/tokenizer.cpp` - 命令或参数
441: `		3rdparty/sonnet/src/ui/highlighter.cpp` - 命令或参数
442: `		3rdparty/sonnet/src/plugins/hunspell/hunspellclient.cpp` - 命令或参数
443: `		3rdparty/sonnet/src/plugins/hunspell/hunspelldebug.cpp` - 命令或参数
444: `		3rdparty/sonnet/src/plugins/hunspell/hunspelldict.cpp` - 命令或参数
445: `	)` - 命令或参数
446: `endif ()` - 条件分支结束
447: `` - 空行
448: `if (WIN32)` - 如果条件 WIN32 成立，进入分支
449: `	add_definitions(-DUNICODE -D_UNICODE)` - 添加编译器预处理定义
450: `` - 空行
451: `	find_package(Qt5 5.15.0 QUIET COMPONENTS WinExtras)` - 查找并加载包：Qt5 5.15.0 QUIET COMPONENTS WinExtras
452: `` - 空行
453: `	if (MSVC)` - 如果条件 MSVC 成立，进入分支
454: `		set(CMAKE_PREFIX_PATH $ENV{QTDIR})` - 设置变量 CMAKE_PREFIX_PATH 为 $ENV{QTDIR}
455: `		set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} /MP")` - 设置变量 CMAKE_CXX_FLAGS_DEBUG 为 ${CMAKE_CXX_FLAGS_DEBUG} /MP
456: `		set(CMAKE_CXX_FLAGS_RELEASE "${CMAKE_CXX_FLAGS_RELEASE} /MP /GL /Zi")` - 设置变量 CMAKE_CXX_FLAGS_RELEASE 为 ${CMAKE_CXX_FLAGS_RELEASE} /MP /GL /Zi
457: `		set(CMAKE_EXE_LINKER_FLAGS_RELEASE "${CMAKE_EXE_LINKER_FLAGS_RELEASE} /LTCG /DEBUG /OPT:REF")` - 设置变量 CMAKE_EXE_LINKER_FLAGS_RELEASE 为 ${CMAKE_EXE_LINKER_FLAGS_RELEASE} /LTCG /DEBUG /OPT:REF
458: `` - 空行
459: `		if (CMAKE_CL_64)` - 如果条件 CMAKE_CL_64 成立，进入分支
460: `			set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} /SUBSYSTEM:WINDOWS /ENTRY:\"mainCRTStartup\"")` - 命令或参数
461: `		else ()` - 否则执行该分支
462: `			set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} /SUBSYSTEM:WINDOWS,5.01 /ENTRY:\"mainCRTStartup\"")` - 命令或参数
463: `		endif ()` - 条件分支结束
464: `	endif ()` - 条件分支结束
465: `` - 空行
466: `	set(OTTER_SOURCES` - 命令或参数
467: `		${OTTER_SOURCES}` - 命令或参数
468: `		otter-browser.rc` - 命令或参数
469: `		src/modules/platforms/windows/WindowsPlatformIntegration.cpp` - 源文件路径
470: `		src/modules/platforms/windows/WindowsPlatformStyle.cpp` - 源文件路径
471: `	)` - 命令或参数
472: `elseif (APPLE)` - 否则如果 APPLE 成立
473: `	find_package(Qt5 5.15.0 QUIET COMPONENTS MacExtras)` - 查找并加载包：Qt5 5.15.0 QUIET COMPONENTS MacExtras
474: `` - 空行
475: `	set(CMAKE_OSX_DEPLOYMENT_TARGET 10.13)` - 设置变量 CMAKE_OSX_DEPLOYMENT_TARGET 为 10.13
476: `	set(MACOSX_BUNDLE_BUNDLE_NAME "Otter Browser")` - 设置变量 MACOSX_BUNDLE_BUNDLE_NAME 为 Otter Browser
477: `	set(MACOSX_BUNDLE_BUNDLE_VERSION ${MAJOR_VERSION}.${MINOR_VERSION}.${PATCH_VERSION})` - 设置变量 MACOSX_BUNDLE_BUNDLE_VERSION 为 ${MAJOR_VERSION}.${MINOR_VERSION}.${PATCH_VERSION}
478: `	set(MACOSX_BUNDLE_LONG_VERSION_STRING ${MAJOR_VERSION}.${MINOR_VERSION}.${PATCH_VERSION})` - 设置变量 MACOSX_BUNDLE_LONG_VERSION_STRING 为 ${MAJOR_VERSION}.${MINOR_VERSION}.${PATCH_VERSION}
479: `	set(MACOSX_BUNDLE_SHORT_VERSION_STRING ${MAJOR_VERSION}.${MINOR_VERSION})` - 设置变量 MACOSX_BUNDLE_SHORT_VERSION_STRING 为 ${MAJOR_VERSION}.${MINOR_VERSION}
480: `	set(MACOSX_BUNDLE_ICON_FILE otter-browser.icns)` - 设置变量 MACOSX_BUNDLE_ICON_FILE 为 otter-browser.icns
481: `	set(MACOSX_BUNDLE_GUI_IDENTIFIER "org.otter-browser.otter-browser")` - 设置变量 MACOSX_BUNDLE_GUI_IDENTIFIER 为 org.otter-browser.otter-browser
482: `	set(MACOSX_BUNDLE_COPYRIGHT "Copyright (C) 2013-2025 Otter Browser Team. All rights reserved.")` - 设置变量 MACOSX_BUNDLE_COPYRIGHT 为 Copyright (C) 2013-2025 Otter Browser Team. All rights reserved.
483: `	set(OTTER_SOURCES` - 命令或参数
484: `		${OTTER_SOURCES}` - 命令或参数
485: `		src/modules/platforms/mac/MacPlatformIntegration.mm` - 源文件路径
486: `		src/modules/platforms/mac/MacPlatformStyle.cpp` - 源文件路径
487: `		resources/icons/otter-browser.icns` - 源文件路径
488: `	)` - 命令或参数
489: `` - 空行
490: `	set_source_files_properties(resources/icons/otter-browser.icns PROPERTIES MACOSX_PACKAGE_LOCATION Resources)` - 命令或参数
491: `elseif (UNIX)` - 否则如果 UNIX 成立
492: `	find_package(Qt5 5.15.0 QUIET COMPONENTS DBus)` - 查找并加载包：Qt5 5.15.0 QUIET COMPONENTS DBus
493: `` - 空行
494: `	if (TARGET Qt5::DBus AND ENABLE_DBUS)` - 如果条件 TARGET Qt5::DBus AND ENABLE_DBUS 成立，进入分支
495: `		add_definitions(-DOTTER_ENABLE_DBUS)` - 添加编译器预处理定义
496: `	endif ()` - 条件分支结束
497: `` - 空行
498: `	set(OTTER_SOURCES` - 命令或参数
499: `		${OTTER_SOURCES}` - 命令或参数
500: `		src/modules/platforms/freedesktoporg/FreeDesktopOrgPlatformIntegration.cpp` - 源文件路径
501: `		src/modules/platforms/freedesktoporg/FreeDesktopOrgPlatformStyle.cpp` - 源文件路径
502: `		3rdparty/libmimeapps/ConfigReader.cpp` - 命令或参数
503: `		3rdparty/libmimeapps/DesktopEntry.cpp` - 命令或参数
504: `		3rdparty/libmimeapps/Index.cpp` - 命令或参数
505: `		3rdparty/libmimeapps/Tools.cpp` - 命令或参数
506: `	)` - 命令或参数
507: `endif ()` - 条件分支结束
508: `` - 空行
509: `feature_summary(WHAT ALL INCLUDE_QUIET_PACKAGES FATAL_ON_MISSING_REQUIRED_PACKAGES)` - 命令或参数
510: `` - 空行
511: `list(LENGTH OTTER_BACKENDS_WEB OTTER_BACKENDS_WEB_LENGTH)` - 命令或参数
512: `` - 空行
513: `if (${OTTER_BACKENDS_WEB_LENGTH} EQUAL 0)` - 如果条件 ${OTTER_BACKENDS_WEB_LENGTH} EQUAL 0 成立，进入分支
514: `	if (ALLOW_WITHOUT_WEB_BACKENDS)` - 如果条件 ALLOW_WITHOUT_WEB_BACKENDS 成立，进入分支
515: `		add_definitions(-DOTTER_NO_WEB_BACKENDS)` - 添加编译器预处理定义
516: `` - 空行
517: `		message(WARNING "No web backends available!")` - 命令或参数
518: `	else ()` - 否则执行该分支
519: `		message(SEND_ERROR "No web backends available!")` - 命令或参数
520: `	endif ()` - 条件分支结束
521: `else ()` - 否则执行该分支
522: `	set(OTTER_BACKENDS_WEB_SUMMARY "The following web backends will be built:\n\n")` - 设置变量 OTTER_BACKENDS_WEB_SUMMARY 为 The following web backends will be built:\n\n
523: `` - 空行
524: `	foreach (_backend ${OTTER_BACKENDS_WEB})` - 循环开始
525: `		set(OTTER_BACKENDS_WEB_SUMMARY "${OTTER_BACKENDS_WEB_SUMMARY} * ${_backend}\n")` - 设置变量 OTTER_BACKENDS_WEB_SUMMARY 为 ${OTTER_BACKENDS_WEB_SUMMARY} * ${_backend}\n
526: `	endforeach ()` - 循环结束
527: `` - 空行
528: `	message(STATUS ${OTTER_BACKENDS_WEB_SUMMARY})` - 命令或参数
529: `endif ()` - 条件分支结束
530: `` - 空行
531: `string(TIMESTAMP BUILD_DATETIME UTC)` - 命令或参数
532: `` - 空行
533: `find_package(Git QUIET)` - 查找并加载包：Git QUIET
534: `` - 空行
535: `set(GIT_BRANCH "unknown")` - 设置变量 GIT_BRANCH 为 unknown
536: `set(GIT_DATETIME "unknown")` - 设置变量 GIT_DATETIME 为 unknown
537: `set(GIT_REVISION "unknown")` - 设置变量 GIT_REVISION 为 unknown
538: `` - 空行
539: `if (GIT_FOUND)` - 如果条件 GIT_FOUND 成立，进入分支
540: `	macro(execute_git OUTPUT COMMAND)` - 命令或参数
541: `		separate_arguments(COMMAND)` - 命令或参数
542: `` - 空行
543: `		execute_process(COMMAND ${GIT_EXECUTABLE} ${COMMAND}` - 命令或参数
544: `			WORKING_DIRECTORY "${CMAKE_SOURCE_DIR}"` - 命令或参数
545: `			OUTPUT_VARIABLE ${OUTPUT}` - 命令或参数
546: `			ERROR_QUIET` - 命令或参数
547: `			OUTPUT_STRIP_TRAILING_WHITESPACE` - 命令或参数
548: `		)` - 命令或参数
549: `	endmacro()` - 命令或参数
550: `` - 空行
551: `	execute_git("GIT_BRANCH" "rev-parse;--abbrev-ref;HEAD")` - 命令或参数
552: `	execute_git("GIT_DATETIME" "show;-s;--format=%ci")` - 命令或参数
553: `	execute_git("GIT_REVISION" "rev-parse;--short;HEAD")` - 命令或参数
554: `endif ()` - 条件分支结束
555: `` - 空行
556: `add_definitions(-DOTTER_BUILD_DATETIME="${BUILD_DATETIME}" -DOTTER_GIT_BRANCH="${GIT_BRANCH}" -DOTTER_GIT_DATETIME="${GIT_DATETIME}" -DOTTER_GIT_REVISION="${GIT_REVISION}")` - 添加编译器预处理定义
557: `` - 空行
558: `add_executable(otter-browser WIN32 MACOSX_BUNDLE` - 命令或参数
559: `	${OTTER_UI}` - 命令或参数
560: `	${OTTER_RESOURCES}` - 命令或参数
561: `	${OTTER_SOURCES}` - 命令或参数
562: `)` - 命令或参数
563: `` - 空行
564: `foreach (_library ${OTTER_LINK_LIBRARIES})` - 循环开始
565: `	target_link_libraries(otter-browser ${_library})` - 链接库
566: `endforeach ()` - 循环结束
567: `` - 空行
568: `if (TARGET Hunspell::Hunspell AND ENABLE_SPELLCHECK)` - 如果条件 TARGET Hunspell::Hunspell AND ENABLE_SPELLCHECK 成立，进入分支
569: `	target_link_libraries(otter-browser Hunspell::Hunspell)` - 链接库
570: `endif ()` - 条件分支结束
571: `` - 空行
572: `if (WIN32)` - 如果条件 WIN32 成立，进入分支
573: `	target_link_libraries(otter-browser Qt5::WinExtras ole32 shell32 advapi32 user32)` - 链接库
574: `elseif (APPLE)` - 否则如果 APPLE 成立
575: `	find_library(FRAMEWORK_Cocoa Cocoa)` - 命令或参数
576: `	find_library(FRAMEWORK_Foundation Foundation)` - 命令或参数
577: `` - 空行
578: `	set_target_properties(otter-browser PROPERTIES OUTPUT_NAME "Otter Browser")` - 命令或参数
579: `` - 空行
580: `	target_link_libraries(otter-browser Qt5::MacExtras ${FRAMEWORK_Cocoa} ${FRAMEWORK_Foundation})` - 链接库
581: `elseif (UNIX)` - 否则如果 UNIX 成立
582: `	if (TARGET Qt5::DBus AND ENABLE_DBUS)` - 如果条件 TARGET Qt5::DBus AND ENABLE_DBUS 成立，进入分支
583: `		target_link_libraries(otter-browser Qt5::DBus)` - 链接库
584: `	endif ()` - 条件分支结束
585: `` - 空行
586: `	if (ENABLE_CRASH_REPORTS)` - 如果条件 ENABLE_CRASH_REPORTS 成立，进入分支
587: `		target_link_libraries(otter-browser -lpthread)` - 链接库
588: `	endif ()` - 条件分支结束
589: `endif ()` - 条件分支结束
590: `` - 空行
591: `target_link_libraries(otter-browser Qt5::Core Qt5::Gui Qt5::Multimedia Qt5::Network Qt5::PrintSupport Qt5::Qml Qt5::Svg Qt5::Widgets)` - 链接库
592: `` - 空行
593: `set(XDG_APPS_INSTALL_DIR ${CMAKE_INSTALL_PREFIX}/share/applications CACHE FILEPATH "Install path for .desktop files")` - 命令或参数
594: `` - 空行
595: `file(GLOB OTTER_TRANSLATIONS resources/translations/*.qm)` - 文件相关操作
596: `` - 空行
597: `foreach (_translation ${OTTER_TRANSLATIONS})` - 循环开始
598: `	install(FILES ${_translation} DESTINATION ${CMAKE_INSTALL_PREFIX}/share/otter-browser/locale/)` - 安装规则
599: `` - 空行
600: `	if (APPLE)` - 如果条件 APPLE 成立，进入分支
601: `		file(COPY ${_translation} DESTINATION "Otter Browser.app/Contents/Resources/locale/")` - 文件相关操作
602: `	endif ()` - 条件分支结束
603: `endforeach ()` - 循环结束
604: `` - 空行
605: `install(FILES resources/icons/otter-browser-16.png DESTINATION ${CMAKE_INSTALL_PREFIX}/share/icons/hicolor/16x16/apps/ RENAME otter-browser.png)` - 安装规则
606: `install(FILES resources/icons/otter-browser-32.png DESTINATION ${CMAKE_INSTALL_PREFIX}/share/icons/hicolor/32x32/apps/ RENAME otter-browser.png)` - 安装规则
607: `install(FILES resources/icons/otter-browser-48.png DESTINATION ${CMAKE_INSTALL_PREFIX}/share/icons/hicolor/48x48/apps/ RENAME otter-browser.png)` - 安装规则
608: `install(FILES resources/icons/otter-browser-64.png DESTINATION ${CMAKE_INSTALL_PREFIX}/share/icons/hicolor/64x64/apps/ RENAME otter-browser.png)` - 安装规则
609: `install(FILES resources/icons/otter-browser-128.png DESTINATION ${CMAKE_INSTALL_PREFIX}/share/icons/hicolor/128x128/apps/ RENAME otter-browser.png)` - 安装规则
610: `install(FILES resources/icons/otter-browser-256.png DESTINATION ${CMAKE_INSTALL_PREFIX}/share/icons/hicolor/256x256/apps/ RENAME otter-browser.png)` - 安装规则
611: `install(FILES resources/icons/otter-browser.svg DESTINATION ${CMAKE_INSTALL_PREFIX}/share/icons/hicolor/scalable/apps/)` - 安装规则
612: `install(FILES otter-browser.desktop DESTINATION ${XDG_APPS_INSTALL_DIR})` - 安装规则
613: `install(FILES packaging/otter-browser.appdata.xml DESTINATION ${CMAKE_INSTALL_PREFIX}/share/metainfo)` - 安装规则
614: `install(FILES man/otter-browser.1 DESTINATION ${CMAKE_INSTALL_MANDIR}/man1/)` - 安装规则
615: `install(TARGETS otter-browser DESTINATION bin/)` - 安装规则
