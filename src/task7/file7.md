### Задание 7

Map<String, Task> loadAllMapped() - Map<String, Task> fetchTasksMap() - получение задач в виде Map

Map<String, List<Comment>> loadAllComments(List<CommentWithAttachment> commentWithAttachments) - Map<String, List<Comment>> fetchCommentsMap(List<CommentWithAttachment> commentWithAttachments) - получение комментов в виде Map

void update(Filter filter) - void updateFilters(Filter filter) - процедура обновления фильтров

List<PrimaryFilter> getPrimaries() - List<PrimaryFilter> getPrimaryFilters() - метод получения первичных фильтров

List<Filter> sortFiltersByName(List<Filter> filters) - List<Filter> getFiltersContainsNamesFromList(List<Filter> filters) - метод получения фильтров, содержащих имена из списка

List<Filter> getData() - List<PrimaryFilter> getPrimaryFilters() - метод получения фильтров

void start() - void startLoadingPrimaryFiltersService() - процедура запуска сервиса по получению фильтров

void zip(List<File> files, String path) - void archiveFilesToZip(List<File> files, String path) - процедура архивации файлов в zip-архив

boolean unpackAndSaveFromComment(InputStream inputStream, Context context, Comment comment) - boolean archiveFilesToZipFromStream(InputStream inputStream, Context context, Comment comment) - архивация данных из потока

void loadTasksFromServer() - void fetchTasks() - процедура получения задач

void send(String id, T task) - void sendTask(String id, T task) - процедура отправки задачи на сервер

void excludeArchiveTasksAndComments() - void removeArchiveTasksAndComments() - процедура удаления архивных задач из общего списка