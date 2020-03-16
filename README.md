# DeviceTypes

This package contains a file wich enumerates different device types, such as:
- iPhoneSE
- iPhone XSMax

The purpose of this package is to speed up the process of setting constraints programmatically,  for different UIScreen sizes. 
To see a clear implementation of this package, have a look at GitHub-Followers project here:  https://github.com/PetreVane/GitHub-followers


Example of setting constrains programmatically for different UIScreen sizes:

    /// Adds image & sets imageView constraints
     func configureLogoView() {
         logoImageView.translatesAutoresizingMaskIntoConstraints = false
         view.addSubview(logoImageView)
         logoImageView.image = Images.logoImage
         
         // sets padding for topConstraint depending on the type of device
         let topConstraintPadding: CGFloat = DeviceTypes.isiPhoneSE || DeviceTypes.isiPhone8Zoomed ? 20 : 80
         
         NSLayoutConstraint.activate([
             logoImageView.topAnchor.constraint(equalTo: view.safeAreaLayoutGuide.topAnchor, constant: topConstraintPadding),
             logoImageView.centerXAnchor.constraint(equalTo: view.centerXAnchor),
             logoImageView.heightAnchor.constraint(equalToConstant: 200),
             logoImageView.widthAnchor.constraint(equalToConstant: 200)
         ])
     }
