local({r <- getOption("repos")
    r["CRAN"] <- "http://cran.revolutionanalytics.com"
    options(repos=r)})
    
options(max.print=100)
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


