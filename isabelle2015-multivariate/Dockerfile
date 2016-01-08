FROM unruh/isabelle:base
RUN /root/build-heap HOL-Multivariate_Analysis
USER user


#USER root
#RUN echo '/^ISABELLE_LOGIC=/c\nISABELLE_LOGIC=HOL-Multivariate_Analysis\n.\nw\n#q' | ed -s /opt/Isabelle2015/etc/settings 
#USER user
#RUN isabelle build -b HOL-Multivariate_Analysis
# TODO: remove intermediate images right after build (same RUN command)
