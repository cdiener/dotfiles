local({r <- getOption("repos")
    r["CRAN"] <- "https://cloud.r-project.org/"
    options(repos=r)})

options(max.print=1000)
options(editor="vim")
options(menu.graphics=FALSE)
options(continue="... ")
utils::rc.settings(ipck=TRUE)

q <- function (save="no", ...) {
    quit(save=save, ...)
}

"%c%" <- function(ex, filename, env=parent.frame()) {
    if (!file.exists(filename)) {
        e <- new.env()
        eval(match.call()$ex, envir = e)
        save(list = ls(e), file = filename, envir = e)
    }

    load(filename, envir=env)
}

update_all <- function(v="3.3") {
    update.packages(lib.loc="~/R/x86_64-pc-linux-gnu-library/%s/", ask=F)
}
