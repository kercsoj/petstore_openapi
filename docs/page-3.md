# Page 3

Arguments:

name
    The filename of the file. Any UTF-8 name is allowed. Path components such as `/` and `\` will be treated as part of the filename, not a path to a sub-folder.

- size
  The size of the file, in bytes. This field is recommended, as it will let you find out if there's a quota issue before uploading the raw file.

content_type
: The content type of the file. If not given, it will be guessed based on the file extension.

parent_folder_id
: The id of the folder to store the file in. An error will be returned if this does not correspond to an existing folder. If this and parent_folder_path are sent an error will be returned. If neither is given, a default folder will be used.

parent_folder_path
: The path of the folder to store the file in. The path separator is the forward slash `/`, never a back slash. The folder will be created if it does not already exist. This parameter only applies to file uploads in a context that has folders, such as a user, a course, or a group. If this and parent_folder_id are sent an error will be returned. If neither is given, a default folder will be used.

folder
: [deprecated] Use parent_folder_path instead.

on_duplicate
: How to handle duplicate filenames. If `overwrite`, then this file upload will overwrite any other file in the folder with the same name. If `rename`, then this file will be renamed if another file in the folder exists with the given name. If no parameter is given, the default is `overwrite`. This doesn't apply to file uploads in a context that doesn't have folders.

success_include[]
: An array of additional information to include in the upload success response. See [Files API](files.html#method.files.api_show) for more information.
