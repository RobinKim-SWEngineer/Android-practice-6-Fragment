# Android-practice-6-Fragment
Creating and adding a fragment to the main layout

`Fragment` is reusable portion of UI. In other words, a *modular section* of an activity. Multiple fragments can be in a single activity for a multi-pane UI, also one fragment can be reused in multiple activities.

When we want to make two different screens, and if they have some **navigational relationship**, we would go for fragment-fragment rather than activity-activity. 

## Adding a Fragment class
 - When you add a Fragment class, a class that *extends Fragment class* will be generated. Take a look at the overriden `onCreateView(..)` method.
 
    ```
    override fun onCreateView(inflater: LayoutInflater, container: ViewGroup?, savedInstanceState: Bundle?)
        : View? {
        // Inflate the layout for this fragment
        return inflater.inflate(R.layout.fragment_title, container, false)
    }
    ```
    This method returns the root view of **inflated view hierarchy** for the fragment. We are going to replace this method with `DataBindingUtil.inflate(..)` so we can use the *binding object* to the layout.

## Creating a binding object to Fragment layout
 - Following `DataBinding.inflate(..)` method will **inflate** the layout and **return** the binding object. `binding.root` contains the inflated view.

    ```
    override fun onCreateView(inflater: LayoutInflater, container: ViewGroup?, savedInstanceState: Bundle?)
        : View? {
        val binding = DataBindingUtil.inflate<FragmentTitleBinding>(inflater, R.layout.fragment_title, container, false)
        return binding.root
    }
    ```

## Adding fragment to the main layout
