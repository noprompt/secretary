# secretary

A client-side router for ClojureScript.

## Usage

In your `project.clj`:

```clojure
[secretary "0.2.0-SNAPSHOT"]
```

Using with your app:

```clojure
(ns myapp
  (:use-macros [secretary.macros :only [defroute]])
  (:require [secretary.core :as secretary]))

(defroute "/users/:id/food/:name" {:as params}
  (.log js/console (str "User: " (:id params) " Food: " (:name params))))

(defroute "/users/:id" {:keys [id]}
  (.log js/console (str "User: " id)))

(secretary/dispatch! "/users/gf3/food/pizza") ; "User: gf3 Food: pizza"
```

## License

Distributed under the Eclipse Public License, the same as Clojure.

